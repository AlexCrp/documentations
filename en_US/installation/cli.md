# Command line installation

# Automatic installation

For an automatic installation, please follow the documentation corresponding to your type of system : 

- On a [VM](https://doc.jeedom.com/en_US/installation/vm)
- On [bearemetal (type Intel Nuc)](https://doc.jeedom.com/en_US/installation/baremetal)

# Manual installation

Here you will find the documentation to install Jeedom on Debian

> **Important**
>
> Debian 10 (Buster) is the officially supported distribution for version 3.3.X or more of Jeedom (but Stretch remains perfectly functional). If you do not have a minimum command of Linux environments, we advise you to start with a Smart.

> **Important**
>
> Installation script can be dangerous because it assumes your system is blank. If not, please read the script and install by hand.

>**TIPS**
>
>To find out the IP of the VM (once connected to it, the identifiers are displayed on the connection screen) ``ip -s -c -h a``

Connect in SSH to your system and do :

````
wget https://raw.githubusercontent.com/jeedom/core/master/install/install.sh
chmod +x install.sh
./install.sh
````

Then just go to ``IP_JEEDOM`` from your internet browser.

> **NOTE**
>
> The default credentials are admin / admin

> **NOTE**
>
> The following arguments can be used : -w = webserver folder -z = installation dependencies z-wave -m = desired mysql root password

````
./install.sh -w /var/www/html -z -m Jeedom
````

Then you can follow the documentation [First step with Jeedom](https://doc.jeedom.com/en_US/premiers-pas/index).
