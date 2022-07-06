# MCO MH-S412 Double

**The module**

![module](images/mco.mhs412/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/mco.mhs412/vuedefaut1.jpg)

## Summary

The MH-S412-EU switch makes it possible to switch the 2 connected loads, either manually like a conventional switch, or remotely via the Z-Wave wireless protocol.

Its glass finish and design brings a modern style.

MH-S412-EU switch can control any type of load, lighting or electrical appliance.

The switch is also equipped with an LED indicator that indicates its status.

## Fonctions

-   Control two lamps or devices remotely
-   Installs in place of an existing switch (fits perfectly into a 40mm flush-mounted box)
-   ON / OFF function
-   Support association commands (Group 1 and Group 2)
-   Control of the two charges locally
-   Status LED
-   Glass finish, modern design
-   Touch buttons

## Technical characteristics

-   Type of module : Z-Wave receiver
-   Color : Blanc
-   Food : 230 V, 50 Hz
-   Wiring : 3 wire, neutral required
-   Maximum power : 5A (1100W) for each channel
-   Frequency : 868.42 Mhz
-   Scope : up to 30 m
-   Dimensions : 86 x 86 x 43 mm
-   Affichage: Blue / red LED

## Module data

-   Mark : MC HOME
-   Name : MH-S412 Double
-   Manufacturer ID : 351
-   Product Type : 16642
-   Product ID : 514

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press one of the 2 buttons on the front panel for 3 sec, according to its paper documentation.

Once included you should get this :

![Plugin Zwave](images/mco.mhs412/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/mco.mhs412/commandes.jpg)

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the parameters tab)

![Config1](images/mco.mhs412/config1.jpg)

Parameter details :

-   1: Saving state before power failure : enable (allows to find the last state of the switches just before the power cut) diseable )

### Groupes

This module has 3 association groups. Only the third is essential.

![Groupe](images/mco.mhs412/groupe.jpg)

## Good to know

### Specificities

- the touch buttons have a blue halo when the load is controlled
- the touch buttons have an orange halo when the load is not controlled
- the touch is rather pleasant and the responsive controls
- this switch can control its load in autonomous mode (not attached to a z-wave controller)

## Wakeup

This module being connected to the mains (220v), the alarm clock is instantaneous and therefore does not require any particular action when changing parameters

## Faq.

To exclude this model, put Openzwave in exclusion mode and press one of the 2 buttons on the front panel for 3 sec, in accordance with its paper documentation.

To restore the factory settings, press one of the 2 buttons on the front panel for 10 sec, in accordance with its paper documentation.
