# Aeotec Panic Button

**The module**

![module](images/aeotec.panicbutton/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/aeotec.panicbutton/vuedefaut1.jpg)

## Summary

This keyfob remote control with a modern and pleasant design has a button to control all types of Z-Wave devices such as lamps, blinds, etc.

With its very small dimensions, you can easily put it in your pocket. Easy to use and elegant, it is equipped with a ring to attach it to keys, which makes it available when leaving the house or when returning to your home.

The button allows you to control two devices or scenes thanks to the management of short and long presses. This remote control can be used as a primary or secondary controller.

This remote control can also be used as an emergency or panic button. In the event of distress or when its holder is faced with another emergency situation, it is enough for him to press the button and a Z-Wave signal will be emitted. In this case, this device can also be used as a medallion around the neck.

## Fonctions

-   Key fob remote control
-   Primary or secondary controller
-   Ultra compact and ultra design
-   1 configurable button
-   Manages up to 2 devices / scenes
-   Can be used as an emergency / panic button
-   Use around the neck as an emergency medallion

## Technical characteristics

-   Type of module : Z-Wave transmitter
-   Food : 1 Lithium 3V CR2450 battery
-   Battery life : 2 to 3 months for 10 to 20 uses per day
-   Frequency: 868.42 MHz
-   Transmission distance : 30m indoors
-   Dimensions : 55 x 30 x 11mm (L x W x H)

## Module data

-   Mark : Aeotec
-   Name : Panic Button
-   Manufacturer ID : 134
-   Product Type : 1
-   Product ID : 38

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the LEARN button, in accordance with its paper documentation.

![inclusion](images/aeotec.panicbutton/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/aeotec.panicbutton/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/aeotec.panicbutton/commandes.jpg)

Here is the list of commands :

-   Buttons : it is the command which will push the button up
  - 1 : Short press button
  - 2 : Long press button

### Configuration of the module

> **IMPORTANT**
>
> During a first inclusion always wake up the module just after the inclusion.

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the Settings tab)

![Config1](images/aeotec.panicbutton/config1.jpg)

Parameter details :

-   250: operating mode of the remote control (absolutely put Scene to use it as a remote control)
-   255 : allows the Keyfob to be reset from the factory

### Groupes

This module has a single association group. It is essential.

![Groupe](images/aeotec.panicbutton/groupe.jpg)

## Good to know

### Specificities

To use this module as a remote control, proceed as follows :

-   1 : Include remote control
-   2 : Wake up the remote control
-   3 : Change parameter 250 to true (do it well even if it already appears in true)
-   4 : Wake up the remote control and make sure that the change has been taken into account
-   5 : Change the operating mode of the remote control by pressing and holding the two buttons on the back for 3 seconds.

##Wakeup

To wake up this module there is only one way :

-   press and hold the LEARN button for 3 seconds

## Faq.
 
This module wakes up by pressing the LEARN button for 3 seconds.

This module is a battery module, the new configuration will not be
take into account that if you wake up the remote control.

## Important note

You have to wake up the module : after its inclusion, after a change in configuration, after a change in wakeup, after a change in association groups
