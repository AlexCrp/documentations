# Installation sur Raspberry Pi

Vous trouverez ici la documentation pour installer Jeedom sur un raspberry Pi **avec une carte MiroSD.**. Il existe 2 modes :

- Automatique (bêta) : utilisation de l'image pour Raspberry Pi faite par Jeedom avec Jeedom de préinstallé dessus
- Ligne de commande : installation manuelle de Jeedom à partir de Raspberry Pi OS

> **Important**
>
> Debian 10 (Buster) est la distribution officiellement supportée.

# Installation automatique

## Télécharger la dernière image

Vous retrouvez les images [ici](https://images.jeedom.com/rpi/)

> **IMPORTANT**
>
>Il y 2 images : jeedom-debian-XXXX-rpi-X.X.XX.zip qui est en 32bits, elle est compatible avec les modèles de Raspberry PI de génération 2 et 3 et jeedom-debian-XXXX-rpi-64-X.X.XX.zip qui est en 64bits, elle est compatible uniquement pour les Raspberry Pi4 et est en alpha (non recommandé).

Raspberry Pi imager permet de télécharger directement l'image d'installation de Raspberry Pi OS, dans sa version la plus récente.

## Gravez cette image sur une carte MicroSD avec Raspberry Pi Imager par exemple

Vous pouvez le télécharger [ici](https://www.raspberrypi.org/downloads/)

## Démarrer le PI

Insérez votre carte MicroSD, branchez le câble réseau et branchez l’alimentation.

> **Important**
>
> Lors du premier démarrage, le Raspberry Pi peut être lent car il redimensionne la partition pour correspondre à la taille de votre carte MicroSD. De plus, une fois le 1er démarrage fait, il est conseillé de redémarrer à nouveau pour que le Swap soit de taille correcte.

Il vous suffit ensuite, depuis votre navigateur, de saisir : http://IP_RPI/ (en remplaçant IP_RPI par l'ip de votre Raspberry Pi).

> **Information**
>
> Les identifiants de connexion SSH par défaut sont : jeedom et Mjeedom96 pour le mot de passe 

Ensuite, vous pouvez suivre la documentation [Premier pas avec Jeedom](https://doc.jeedom.com/fr_FR/premiers-pas/index)

# Installation en ligne de commande

## Télécharger la dernière image "lite"

[ici](https://downloads.raspberrypi.org/raspbian_lite_latest)

Raspberry Pi Imager permet de télécharger directement l'image d'installation de Raspberry Pi OS, dans sa version la plus récente.

## Gravez cette image sur une carte MiroSD avec Raspberry Pi Imager par exemple

[ici](https://www.raspberrypi.org/downloads/)

> **Note**
>
> Si vous utilisez Etcher pour graver votre image, l’étape de décompression est inutile (format Zip reconnu directement dans la sélection du fichier image).

## Activer un accès SSH

> **Warning**
>
> Pour des raisons de sécurité, l’accès SSH n’est plus activé par défaut sur cette distribution. Il faut donc l’activer.

Il faut créer sur la partition boot (la seule accessible sous Windows) un fichier ssh vide.

Il suffit de faire un clic droit : nouveau / document texte et le renommer en "ssh" **sans extension**

> **Important**
>
> Sous Windows, dans l’explorateur, il faut donc vérifier votre paramétrage dans affichage / options / modifier les options de dossiers et de recherche /

![ExtensionFichier](images/ExtensionFichier.PNG)

## Démarrer le Raspberry Pi

Insérez votre carte MicroSD, branchez le câble réseau et branchez l’alimentation.

## Se connecter en SSH

Identifiez votre Raspberry Pi sur le réseau

Il faut connaître l’adresse Ip de votre Raspberry PI. Plusieurs solutions :

-   Consultez la configuration DHCP dans votre routeur
-   Utilisez un scanner de port type "Angry IP Scanner" [ici](http://angryip.org/download/#windows)

Etablir la connexion

Ensuite, utilisez par exemple PuTTY pour établir votre connexion [Ici](http://www.putty.org/)

Rentrez l’adresse IP de votre Raspberry Pi (ici 192.168.0.10) et cliquez sur open. Acceptez le message par défaut relatif à la sécurité lors de la première connexion.

Connectez-vous avec les identifiants **pi / raspberry**

> **Important**
>
> Pour des raisons de sécurité, il est impératif de modifier le mot de passe par défaut. Les cas de piratages basés sur l’exploitation du couple login/mot de passe par défaut du Raspberry Pi sont particulièrement répandus. (commande : passwd et sudo passwd)

## Lancer le script d’installation jeedom

``wget -O- https://raw.githubusercontent.com/jeedom/core/master/install/install.sh | sudo bash``

**Le mot de passe sudo est également raspberry**

> **Note**
>
> En fonction de votre débit internet, l’installation peut prendre de 45 à 90 minutes. Vous ne devez surtout pas interrompre le processus avant la fin. A défaut, il faudra reprendre la totalité de la procédure.

Il vous suffit ensuite d’aller sur IP\_MACHINE\_JEEDOM

> **Note**
>
> Les identifiants par défaut sont admin/admin

> **Note**
>
> Les arguments suivants sont utilisables : -w = dossier webserver -z = installation dependances z-wave -m = mot de passe root mysql désiré

````
./install.sh -w /var/www/html -z
````

## Optimisation du système

Si vous utilisez votre Raspberry Pi pour Jeedom sans écran connecté, il est recommandé d'affecter le minimum de RAM à la partie vidéo.

Il suffit de se connecter en **SSH** et de modifier le fichier config : ``sudo nano /boot/config.txt``

Ajoutez **et/ou** De-commentez (en supprimant le #) **et/ou** Modifiez les lignes :

````
gpu_mem=16
disable_l2cache=0
gpu_freq=250
````

Quittez en sauvegardant : ``CTRL+X`` puis ``O`` puis ``ENTER``

Rebootez votre Raspberry Pi

Ensuite, vous pouvez suivre la documentation [Premier pas avec Jeedom](https://doc.jeedom.com/fr_FR/premiers-pas/index)
