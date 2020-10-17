# Edisio EOS 200

**The module**

![eos200.module](images/eos200/eos200.module.jpg)

**The Jeedom visual**

![eos200.vue defaut](images/eos200/eos200.vue-defaut.jpg)

## Summary

Placed on a door, window, garage door, drawer, all opening, this compact and discreet sensor will allow you to know the state of opening or closing of the latter.

Depending on the state, the sensor controls the switching on or off of your lights, closing or opening of the shutters, or even the triggering of an alarm via a scenario.

The signal is only sent when the sensor is separated from its magnetic element. Integrated LED indicator signals all status changes. Low battery level signaled by 3 audible "beeps" on the receiver

## Fonctions

-   Battery-powered wireless magnetic sensor
-   Detects openings / closings
-   Ultra compact
-   Easy and free installation
-   Signal transmitted instantly when opening / closing
-   Self-protection when pulling
-   Battery level information
-   Wall mounting by screws or double-sided tape

## Technical characteristics

-   Type of module : Edisio transmitter
-   Food : 3VDC (Lithium battery ER14250)
-   Frequency : 868.3 MHz
-   Operating temperature : 0 ° C + 45 ° C
-   Scope in free field : 100M
-   Dimensions : 25x79x19mm
-   Degree of protection : IP20
-   Use : Indoors

## Module data

-   Mark : Edisio Smart Home
-   Last name : EOS-200

## General configuration

To configure the Edisio plugin and associate a module with Jeedom, refer to this [documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/edisio/).

> **Important**
>
> So that Jeedom automatically creates your transmitter modules, don't forget to activate the option in the plugin configuration.

### Button "E"

You will find below the button "E" which is the button of association of the temperature sensor.

![eos200.bouton e](images/eos200/eos200.bouton-e.jpg)

### Configuration

By default, the sensor is configured as NO (Normally Open)

![eos200.nf no](images/eos200/eos200.nf-no.jpg)

> **Note**
>
> You will therefore need to configure your sensor, if you want to have a widget with a closed door when it is.

![eos200.mode](images/eos200/eos200.mode.jpg)

## Association of the sensor with Jeedom

Pairing the motion sensor is easy as pie. Just press the "E" button, located under the sensor. This will be recognized automatically by Jeedom. You just have to go to the Edisio plugin. You can then place it in an object, give it a name and save.

Once you've paired your gear, you should get this :

![eos200.general](images/eos200/eos200.general.jpg)

> **Tip**
>
> So that the widget is present on the dashboard, remember to place your equipment in an object.

### Orders 

Once your equipment is created, you should get the commands associated with the module :

![Orders](images/eos200/eos200.commandes.jpg)

Here is the list of commands :

-   Door : This is the command that indicates whether the door is open or closed
-   Drums : Indicates battery status

### Informations

Once your equipment is associated with Jeedom, various information will be available :

![Orders](images/eos200/eos200.informations.jpg)

-   Creation : Indicates the date on which the equipment was created
-   Communication : Indicates the last communication recorded between Jeedom and the module
-   Drums : Indicates the battery status of battery modules
-   Status : Returns the status of the module

## Alternative visual

![eos200.vue alternative](images/eos200/eos200.vue-alternative.jpg)
