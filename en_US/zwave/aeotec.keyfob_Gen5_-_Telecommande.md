# Aeotec Keyfob Gen5

**The module**

![module](images/aeotec.keyfob-gen5/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/aeotec.keyfob-gen5/vuedefaut1.jpg)

## Summary

The Aeon Labs keychain remote control with a modern and pleasant design has 4 buttons allowing you to control any type of Z-Wave device such as lamps, blinds, etc.

With its very small dimensions, you can easily put it in your pocket. Easy to use and elegant, it is equipped with a ring to attach it to keys, which makes it available when leaving the house or when returning to your home.

Each button allows you to control two devices or scenes thanks to the management of short and long presses. This remote control can be used as a primary or secondary controller.

And because the Keyfob Gen5 key fob is part of the Gene range from Aeotec, it surpasses everything that existed before. It uses the latest Z-Wave 500 series chip, offering a 50% increase in radio range and 250% faster communication speed compared to previous Z-Wave products.

## Fonctions

-   Key fob remote control
-   Primary or secondary controller
-   Ultra compact and ultra design
-   4 configurable buttons
-   Manages up to 8 devices / scenes
-   Sliding protection flap
-   Part of the Gen5 range from Aeon Labs
-   Security of radio communication via AES-128 encryption
-   Integrates the Z-Wave 500 series chip
-   250% faster communication compared to standard Z-Wave devices
-   Optimization of the antenna, range 100 meters
-   Ease of use and installation

## Technical characteristics

-   Type of module : Z-Wave transmitter
-   Food : 1 Lithium 3V CR2450 battery
-   Battery life : 1 year
-   Frequency: 868.42 MHz
-   Transmission distance : 100m in open field
-   Operating temperature : -10 ° C to 50 ° C
-   Dimensions : 55 x 30 x 13mm (L x W x H)

## Module data

-   Mark : Aeotec
-   Name : ZW088 Key Fob Gen5
-   Manufacturer ID : 134
-   Product Type : 1
-   Product ID : 88

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the LEARN button, in accordance with its paper documentation.

![inclusion](images/aeotec.keyfob-gen5/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/aeotec.keyfob-gen5/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/aeotec.keyfob-gen5/commandes.jpg)

Here is the list of commands :

-   Buttons : it is the command which will push the button up
  - 1 : Button 1 short press
  - 2 : Button 1 long press
  - 3 : Button 2 short presses
  - 4 : Button 2 long presses
  - 5 : Button 3 short presses
  - 6 : Button 3 long presses
  - 7 : Button 4 short presses
  - 8 : Button 4 long presses

### Configuration of the module

> **IMPORTANT**
>
> During a first inclusion always wake up the module just after the inclusion.

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the Settings tab)

![Config1](images/aeotec.keyfob-gen5/config1.jpg)

Parameter details :

-   250: operating mode of the remote control (absolutely put Scene to use it as a remote control)
-   255 : allows the Keyfob to be reset from the factory

### Groupes

This module has two association groups, the first is the only essential.

![Groupe](images/aeotec.keyfob-gen5/groupe.jpg)

##  Good to know

### Specificities

To use this module as a remote control, proceed as follows :

-   1 : Include remote control
-   2 : Wake up the remote control
-   3 : Change parameter 250 to Scene
-   4 : Wake up the remote control and make sure that the change has been taken into account
-   5 : Change the operating mode of the remote control by pressing the two buttons on the back for 3 seconds.

## Wakeup

To wake up this module there is only one way :

-   press and hold the LEARN button for 3 seconds

## Faq.

This module wakes up by pressing the LEARN button for 3 seconds.

This module is a battery module, the new configuration will only be taken into account if you wake up the remote control.

## Important note

You have to wake up the module : after its inclusion, after a change in configuration, after a change in wakeup, after a change in association groups
