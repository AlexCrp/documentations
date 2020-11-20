# Implementación de Jeedom DNS

## Objectif

Configure Jeedom DNS para que tenga acceso a su Jeedom externamente a través de una URL HTTPS

> **Importante**
>
>El Jeedom DNS actúa como un proxy inverso, por lo que solo le da acceso a su Jeedom en https, por lo tanto, no será posible acceder a su jeedom en SSH de forma remota con el Jeedom DNS

## Requisitos previos

Para tener acceso a Jeedom DNS es absolutamente necesario tener un paquete de servicio de energía o más.

## Principe

El principio de DNS de Jeedom es muy simple, su Jeedom se conectará a uno de nuestros servidores VPN (conexión cifrada). Entonces este servidor en cuestión con nosotros hace "proxy inverso" durante la solicitud : toma su solicitud para conectarse a su libertad y se la transfiere.

Este principio tiene la ventaja de no exponer su Jeedom en Internet, no hay apertura de puerto para hacer.

> **Importante**
>
> Para que esto funcione, su caja debe permitir una conexión saliente en los puertos 1194,1195,1996,1997,1198,1199,2000 y 2001 en UDP. En particular, para el Huawei Livebox y el enrutador 4g, debe reducir el nivel del firewall, para las personas gratuitas también a veces tiene que cambiar a una IP fija (de lo contrario, compartir su IP entre varios usuarios es gratis) Freebox Delta tienes que desactivar el control parental 

## Configurar

### Jeedom

Ahí es súper simple, debe conectar su Jeedom al mercado (consulte la documentación del primer paso). 

Luego, en su Jeedom, en su administración, vaya a la pestaña Redes y marque "Usar DNS de Jeedom" y luego guarde.

Jeedom iniciará el DNS y le dará su URL de acceso a su Jeedom

> **Importante**
>
> Puede cambiar esta URL yendo a la página de perfiles de su mercado, luego a mis pestañas de servicios y haga clic en configuración en "Acceso remoto fácil", en el campo DNS puede personalizarla. Después del registro, debe reiniciar DNS en Jeedom (Sistema -> ajuste -> configuración, luego la pestaña Redes y reiniciar en la sección "Mercado DNS (proxy)"")

Aquí está su Jeedom accesible desde el exterior en https

## FAQ

> **¿Hay necesidad de abrir puertos en mi caja?**
>
> No, no hay necesidad de abrir un puerto desde su caja de internet a su Jeedom. La conexión está en la dirección Jeedom -> VPN, por lo que es una conexión saliente (en los puertos 1194,1195,1996,1997,1198,1199,2000 y 2001) y no una conexión entrante.

> **¿Por qué Jeedom DNS protege mi acceso?**
>
> Jeedom DNS le permite configurar algo muy importante, el acceso HTTPS, esto garantiza que la conexión entre su navegador y su Jeedom esté encriptada, además el certificado es válido, nadie podrá suplantar su Jeedom. Finalmente, la conexión VPN en su Jeedom y nuestros servidores también está encriptada.

> **Cambié el puerto de escucha interno de mi Jeedom y el Jeedom DNS ya no funciona**
>
> De hecho, el DNS de Jeedom solo funciona si su Jeedom escucha en el puerto local 80 (todos los demás puertos están cerrados en la interfaz VPN cuando se conecta). Esto no plantea problemas de seguridad porque la VPN crea un túnel encriptado, por lo que incluso si el flujo está libre en el puerto 80, está encriptado en el túnel VPN.

> **No tengo la página de inicio de sesión pero no puedo iniciar sesión**
>
> Compruebe que ha cambiado las credenciales predeterminadas de jeedom (admin / admin) y que su usuario no está restringido solo localmente.

> **Mi configuración es buena pero imposible tener una página que da vuelta infinitamente**
>
> Si su configuración es correcta (Secuencia de inicialización completada en el registro openvpn_DNS_Jeedom) pero no puede obtener la página de inicio de sesión que funciona aleatoriamente con la aplicación móvil y está en 4g o al final de la línea ADSL. En este caso, debe marcar la casilla en la configuración de red de jeedom como lo que está en 4g y reiniciar el dns como ese jeedom cambiará el mtu de su conexión para reducir el tamaño de los paquetes. Dependiendo de las versiones de Jeedom, esta opción es administrada automáticamente por el núcleo (y por lo tanto no aparece) solo reinicie el DNS.

> **Tengo el error "ERROR: No se puede abrir TUN / TAP dev / dev / net / tun: No existe tal archivo o directorio (errno = 2)"**
>
> Este error generalmente ocurre en instalaciones de tipo acoplador, como se indica en la documentación para [compatibilidad](https://doc.jeedom.com/es_ES/compatibility/) el soporte de Docker es beta precisamente por este tipo de problema. La solución generalmente es instalar openvpn en el host (cuando sea posible)
