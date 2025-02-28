# Complemento de Enedis

Complemento que permite la recuperación de datos de consumo eléctrico de contadores inteligentes *(linky por ejemplo)* cuestionando el [cuenta cliente **Enedis**](https://mon-compte.enedis.fr/auth/XUI/#login/&realm=/enedis&forward=true){:target = "\_ en blanco"}.

>**Importante**
>
>El complemento se reescribió por completo en febrero de 2021 para usar **la API oficial de Enedis Data-Connect**. Si usó el complemento antes, lo invitamos a crear un nuevo equipo o eliminar todos los controles de un equipo anterior.

Es posible acceder a datos desde **consumo**, de **producción** oa los 2 tipos de medición directamente en un dispositivo.

Se reportan 5 datos para cada tipo de medición :
- el **consumo por hora** por media hora *(en kW)*.
- el **consumo diario** *(en kWh)*.
- el **consumo mensual** *(en kWh)*.
- el **consumo anual** *(en kWh)*.
- el **máximo poder** *(en kVA)*.

>**INFORMACIÓN**  
>    
>Como los datos no están disponibles en tiempo real, el complemento recupera los datos de consumo de electricidad del día anterior a cada día.

Siempre que el complemento no haya recuperado todos los datos del día anterior, continúa sondeando los servidores de Enedis cada hora entre las 7 a.m. y las 8 p.m., de lo contrario, las llamadas se suspenden hasta el día siguiente.

# Configuration

Como cualquier complemento de Jeedom, el complemento **Enedis** debe activarse después de la instalación.

## Gestión de la dependencia

El complemento requiere la presencia del paquete de Linux `php-mbstring` normalmente presente de forma predeterminada, por lo que el estado de dependencia debe ser **Bueno** tan pronto como se instale el complemento. De lo contrario, haga clic en el botón **Reanimar** para instalar el paquete que falta.

## Configuración del plugin

Si aún no lo ha hecho, comience por autorizar el intercambio de datos de Enedis con Jeedom haciendo clic en el botón **Autorizar el acceso a los servidores de Enedis : Accedo a mi área de clientes de Enedis** desde la página de configuración del complemento :      

![Lien espace-client Enedis](./images/link_enedis.png)

A continuación, se le redirige a esta página en la que debe informar **sus datos de inicio de sesión para el mercado de Jeedom** luego haga clic en el botón **Validar** :      

![Authentification compte Market Jeedom](./images/Auth_Jeedom.png)

Redirección a la página de consentimiento de Enedis en la que es necesario **marcar la casilla** y haga clic en **Validar** :     

![Autorisation Enedis](./images/Auth_Enedis.png)

Una vez que se valida el intercambio de datos, se muestra esta página :     

![Succès](./images/Auth_Enedis_success.png)

>**Importante**
>    
>Si no puede acceder a ninguna de estas páginas, desactive el bloqueador de anuncios del navegador.

## Configuración del equipo

Para acceder a los diferentes equipos **Enedis**, ir al menú **Complementos → Energía → Enedis**.

>**INFORMACIÓN**
>    
>El botón **+ Agregar** le permite agregar un nuevo medidor / PDL.

Una vez que se haya autorizado el intercambio de datos desde la página de configuración del complemento, todo lo que tiene que hacer es ingresar **el número de identificación del Punto de Entrega** preocupado *(PDL)* y el **tipo de medida** volver.

Durante la primera copia de seguridad de un dispositivo activo y configurado, el complemento creará automáticamente los comandos necesarios e integrará los historiales disponibles en el sitio de Enedis desde el 1 de enero del año en curso. Es probable que este proceso tarde varios minutos, puede seguir el progreso desde el menú **Análisis → Registros** *(inicia sesión ``debug``)*.

>**CONSEJO**
>
>Si por un motivo u otro el plugin no pudo recuperar los historiales al crear los pedidos, bastará con borrar los pedidos y luego guardar el equipo para generar los pedidos y su historial nuevamente.

>**INFORMACIÓN**
>
>Los datos de consumo por hora se recuperan durante los últimos 7 días como máximo.

## Agregar datos

Es posible integrar historias bajo demanda, hasta 3 años atrás, directamente desde el sitio de Enedis. Para hacerlo, simplemente haga clic en el botón azul **Adiciones históricas** desde la pestaña **Pedidos** de un equipo, en la columna **Acción** de la orden en cuestión :

![Ajout d'historiques](./images/enedis_addHistory.png)

Luego elija la fecha de inicio y haga clic en **Bueno** para iniciar el proceso.

Los datos de día, mes, año y potencia máxima se integrarán desde la fecha elegida hasta el 1 de enero del año en curso. Los datos horarios, cuando lo sean, se integrarán hasta 7 días después de la fecha elegida.

>**INFORMACIÓN**
>
>Estas limitaciones de tiempo las establece Enedis.

# Plantilla de widget

>**INFORMACIÓN**
>     
>La plantilla del widget se mostrará en las versiones de escritorio y móvil.

El complemento ofrece la posibilidad de mostrar datos de consumo y / o producción en una plantilla de widget imitando la apariencia de un medidor *Linky*. El clic en el botón "**- \| +**" permite pasar del consumo a la producción para quienes tienen acceso a 2 tipos de medidas.

![Plantilla de widget](./images/enedis_screenshot1.png)

Para activar esta opción, simplemente marque la casilla **Plantilla de widget** en la página general del equipo en cuestión. Una vez que la casilla está marcada, una opción le permite seleccionar el color de fondo del widget *(163, 204, 40 por defecto)*.

>**CONSEJO**
>     
>En la versión de escritorio, la información que se muestra en el widget se adapta en tamaño al cambiar el tamaño del mosaico.
