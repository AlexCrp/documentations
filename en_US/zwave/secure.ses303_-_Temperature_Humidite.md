# Secure SES 303 "Temperature / Humidity"

**The module**

![module](images/secure.ses303/module.jpg)

**The jeedom visual**

![vuedefaut1](images/secure.ses303/vuedefaut1.jpg)

## Summary

The SES303 probe allows the measurement of indoor ambient temperature as well as humidity. It is powered by 2 AA batteries and is Z-Wave Plus certified. In addition to its main function, it is possible to wire various external SECURE probes on the module, either:

-   An external NTC temperature sensor (SES001)
-   4 wired temperature sensors for hose or tank (SES002) connected by 1m cables
-   1 wired temperature sensor for hose or tank (SES003) connected by a 4m cable

These modules are perfect for temperature measurement in central heating control applications or any similar application. Its user interface is simple, with a local push button and an indication LED on the rear side. You can easily include / exclude it in a Z-Wave network.

## Fonctions

-   Precise measurement of temperature and humidity
-   Application in dynamic control systems of tanks / tubes / heated floors /…
-   Possibility to connect external sensors
-   Interoperable with Z-Wave certified products and systems
-   Quick and easy installation
-   Low battery report

## Technical characteristics

-   Type: Portable / wall mount
-   Temperature measurement range: ± 0.5 ° C for 0 ° C to 40 ° C
-   Z-Wave Plus chip
-   Frequency : 868.42 Mhz
-   Alimentation: 2x AA batteries (LR6)
-   Scope : up to 100 m in free field
-   Protection sign : IP30
-   Dimensions : 86 x 85 x 30 mm

## Module data

-   Mark : Horstmann
-   Name : SES 303 Temperature and Humidity Sensor
-   Manufacturer ID : 89
-   Product Type : 13
-   Product ID : 3

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the button on the back for 1 second and release, according to its paper documentation.

![inclusion](images/secure.ses303/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/secure.ses303/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/secure.ses303/commandes.jpg)

Here is the list of commands :

-   Temperature : it is the temperature measurement command
-   Humidity : it is the humidity measurement control
-   Drums : it's the battery command

Several non visible temperatures are also available and will be useful if you have connected external probes

### Configuration of the module

> **IMPORTANT**
>
> During a first inclusion always wake up the module just after the inclusion.

Then it is necessary to configure the module according to your installation. To do this, go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the parameters tab)

![Config1](images/secure.ses303/config1.jpg)

Parameter details :

-   1: Allows you to set how much the temperature must vary for the module to send it to Jeedom (in steps of 0.1)
-   2: Set the time interval for sending the temperature to Jeedom (in minutes)
-   3: Allows you to set how much the humidity must vary for the module to send it to Jeedom (by%)
-   4: Allows you to set the time interval for sending humidity to Jeedom (in minutes)

All the other parameters are identical and correspond to all the external probes possibly connected

### Groupes

This module has only one association group, it is essential

![Groupe](images/secure.ses303/groupe.jpg)

## Wakeup

To wake up this module, press the button on the back once

Important note
---------------

> **IMPORTANT**
>
> You have to wake up the module : after its inclusion, after a change in configuration, after a change in wake up, after a change in association groups
