# Gestión de widgets de complementos

Hay varias posibilidades para crear widgets personalizados para complementos :

- el primero con la función toHtml (método de instancia) que hereda de la clase eqLogic
- por el sistema de plantillas (solo v4)

## Función ToHtml

Entonces, nada especial, la función toHtml debe devolver el widget en html, tienes un ejemplo [el](https://github.com/jeedom/plugin-weather/blob/beta/core/class/weather.class.php#L647)

Lo importante son sobre todo las primeras líneas :

````
$replace = $this->preToHtml($_version);
if (!is_array($replace)) {
	return $replace;
}
````

La función preToHtml devuelve :

- una cadena si el widget está almacenado en caché (si está almacenado en caché, significa que no ha habido cambios desde la última generación, por lo que también puede devolverlo inmediatamente)
- una tabla con los reemplazos principales, tienes la lista [aquí](https://github.com/jeedom/core/blob/alpha/core/class/eqLogic.class.php#L663)

## El sistema de plantillas

El sistema de plantilla de widgets en el código es exactamente el mismo que el de la página Herramientas -> Widget de jeedom.

Aquí un ejemplo :

````
public static function templateWidget(){
	$return = array('info' => array('string' => array()));
	$return['info']['string']['state'] = array(
		'template' => 'tmplmultistate',
		'test' => array(
			array('operation' => '#value# == 2','state' => '<i class="icon maison-vacuum6"></i>'),
			array('operation' => '#value# == 3','state' => '<i class="fa fa-pause"></i>'),
			array('operation' => '#value# > 3 || #value# < 2','state' => '<i class="fa fa-home"></i>')
		)
	);
	return $return;
}
````

Aquí, crearemos un nuevo widget basado en la plantilla "tmplmultistate" (tienes la lista de plantillas [aquí](https://github.com/jeedom/core/tree/alpha/core/template/dashboard) son aquellos con tmpl en su nombre), para un comando de tipo de información y debajo de tipo de cadena.

> **Importante**
>
> Cada plantilla es para un tipo y subtipo determinados, por lo que debe verificar que la plantilla que desea usar exista para el tipo y subtipo

Luego, como es una plantilla con varios estados, hay que definir los iconos según el estado. Se realiza en la parte de prueba de la tabla.

Ejemplo : para la primera prueba, decimos que si el valor del comando vale 2, entonces será necesario reemplazar la etiqueta #\_state_# (en el código html de la plantilla) por </i>

Otro ejemplo basado en otra plantilla podría ser :

````
public static function templateWidget(){
	$return = array('info' => array('string' => array()));
	$return['info']['binary']['toto'] = array(
		'template' => 'tmplicon',
		'replace' => array(
			'#_icon_on_#' => '<i class=\'icon_green icon jeedom-porte-ferme\'></i>',
			'#_icon_off_#' => '<i class=\'icon_red icon jeedom-porte-ouverte\'></i>'
			)
	);
	return $return;
}
````

Aquí, creo un widget toto basado en la plantilla "tmplicon" en tipo de información y subtipo binario. Cuando sea 1, el icono será <i class='icon_green icon jeedom-porte-ferme'></i> y cuando sea 0, será </i>

>**Consejos**
>
> Pequeño consejo, puede en lugar de un icono poner una etiqueta de imagen (preste atención a la ruta)

Luego para usar tu widget :

````
$cmd->setTemplate('dashboard','neato::state');
$cmd->setTemplate('mobile','neato::state');
````

Es como un widget normal, excepto por el nombre del widget que tiene el formato id_plugin::nombre_widget. Para el segundo ejemplo, será id_plugin::toto


