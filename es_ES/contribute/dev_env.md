## Entorno de desarrollo

Veremos aquí cómo configurar un entorno de desarrollo eficiente entre una Pi de prueba y una PC con Windows para la edición de código y el mantenimiento del repositorio de GitHub.

Esta página se refiere a Jeedom Core, pero este método se puede usar para el desarrollo de complementos.

Por supuesto, para ediciones rápidas de algunos archivos, puede usar el complemento **jeeexplorador** directamente en Jeedom. Pero es rápidamente tedioso y luego tienes que transferir todos los cambios al repositorio local o directamente a GitHub. No es lo mas practico.

### Principe

- Configure un Pi de prueba con Jeedom y un recurso compartido de Samba para acceder desde la PC.
- Duplicar el repositorio localmente con **Fusión sublime**.
- Poner en marcha **Texto sublime** para la edición de código de repositorio con sincronización en la prueba Pi.

**Fusión sublime** y **Texto sublime** ciertamente están pagando (un precio bajo con 3 años de actualización), pero son muy ligeros, rápidos, fácilmente personalizables y muy completos sin requerir muchos complementos/paquetes. Además, si no toma una licencia, puede usarlas normalmente, solo tendrá una pequeña ventana emergente de vez en cuando con un botón *Cancelar* !

Este método también es posible con otras herramientas, como **Átomo** (que requerirá algunos paquetes) y **Escritorio GitHub**.

### Prueba/Desarrollo Pi

Lo primero que debe hacer si está desarrollando funciones principales o un complemento : Establecer una configuración de prueba. De hecho, no desarrollamos en una configuración de producción !

Para la instalación de Jeedom, el documento está allí : [Instalación en Raspberry Pi](https://doc.jeedom.com/es_ES/installation/rpi).

Atención, prefiera un SSD a una tarjeta SD !

Una vez que Jeedom esté instalado, instale Samba, en SSH :

`sudo apt-get install samba -y`

Configure una contraseña para www-data (la raíz de Jeedom) :

`sudo smbpasswd www-data` luego ingrese su *contraseña*.

Editar configuración de samba :

`sudo nano /etc/samba/smb.conf`

Agregar :

````text
gana apoyo = sí

[JeedomRoot]
ruta = /var/www/html
navegable = sí
escribible = sí
forzar usuario=www-datos
forcegroup = www-datos
solo lectura = no
invitado ok = si
````

Et redémarrez samba:

`sudo /etc/init.d/smbd restart`

Sous Windows, dans un explorateur de fichier, entrez l'adresse IP du Pi `\\192.168.x.x`

Faites un clic droit sur `jeedomRoot` puis `Connecter un lecteur réseau...`

Sous Windows, vous avez donc maintenant un Disque Réseau `jeedomRoot` !


### Mise en place du repository local

Pour dupliquer le repository en local y pouvoir travailler dessus, nous allons récupérer [Fusión sublime portable](https://www.sublimemerge.com/download).

Récupérer également [Texto sublime portable 64bit](https://www.sublimetext.com/3).

Décompressez les deux archives y placez les dans `C:\Program Files`.

Indiquez à **Fusión sublime** l'éditeur de fichiers :

{% include lightbox.html src="images/sbm_settings1.jpg" data="settings" title="Editeur de fichiers" imgstyle="width:450px;display: block;margin: 0 auto;" %}

Puis clonez le repository. Ici, si vous avez les droits sur le repository du Core, clonez le, sinon *forkez* le sur votre compte GitHub y clonez votre *fork*.

**File / Clone Repository ...**

{% include lightbox.html src="images/sbm_clonerepo.jpg" data="settings" title="Clone Repository" imgstyle="width:450px;display: block;margin: 0 auto;" %}


### Mise en place de l'édition

Dans **Texto sublime**, *Project* / *Edit Project*, définissez le répertoire de votre repository :

````json
{
  "folders":
  [
    {
      "name": "__GitHub Jeedom Core__",
      "path": "W:\\_GitHub-Repos_\\JeedomCore"
    },
    {
      "name": "___Pi_JeedomAlpha___",
      "path": "\\\\192.168.0.110\\jeedomRoot"
    }
  ]
}
````

Aquí agregar la ruta de la prueba Pi no es obligatorio, pero siempre es conveniente.

Así que ahora puedes, en **Texto sublime**, edite directamente los archivos del repositorio local. Los cambios a estos archivos aparecerán en **Fusión sublime**, donde puede confirmar todo o parte de cada archivo, o revertir los cambios si eso no funciona.

Ahora queda probar estos cambios de código en la prueba Jeedom.

Para eso, por supuesto, puede copiar los archivos modificados a su Pi usando el recurso compartido de samba en su PC. O no ! Cuando modifica una docena de archivos en diferentes lugares, rápidamente se volverá doloroso !

Por lo tanto, configuraremos **Texto sublime** para que cuando guardes un archivo, lo copie directamente a la Pi !

Ir al directorio `C:\Program Files\SublimeText3\Data\Packages\User` y cree un archivo `onSaveCopy.py`. Edítelo y, después de modificar las rutas correctas, guarde el siguiente código:

````py
importar sublime, sublime_plugin, sistema operativo
desde el archivo de copia de importación shutil

gitHub_repoCore = "W:\\_GitHub-Repos_\\JeedomCore"
rpi_root = "\\\\192.168.0.110\\JeedomRoot"

clase EventListener(sublime_plugin.Detector de eventos ):
  def on_post_save_async(self, ver):
    fullPath = view.file_name()
    ruta, baseName = os.path.split(fullPath)
    si gitHub_repoCore en la ruta:
      rpi_path = ruta completa.reemplazar (gitHub_repoCore, rpi_root)
      copyfile(ruta_completa, ruta_rpi)
````

Et voilà !

A chaque fois que vous sauvez un fichier, si celui-ci fait partie du repository local, **Texto sublime** va également le copier au bon endroit sur votre Pi. Ctrl-S, F5 sur le Pi y voilà ! Si tout est bon, stage/commit/push dans **Fusión sublime**.

Si vous annulez des modifications, en faisant un *Discard* dans **Fusión sublime**, pensez à faire un clic-droit, *Open in Editor*, y Ctrl-S pour le remettre sur le Pi.

Et bien sûr, attention quand vous mettez à jour le Pi, vous allez écraser les fichiers du Core que vous avez modifié.


Vous pouvez bien sûr suivre la même méthode pour mettre en place vos repository y synchronisation sur vos plugins.