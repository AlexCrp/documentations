# Philio PSP01

**The module**

![module](images/philio.psp01/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/philio.psp01/vuedefaut1.jpg)

## Summary

The PSP01 detector offers 3 different functions : motion detection, temperature sensor and light sensor.

This detector can be used for security or for automation. When the detector is associated with security devices, it serves as an alert trigger by detecting changes in the infrared radiation levels. If a person moves within the detector's field of vision, a radio signal is transmitted, which triggers an alarm to deter intruders.

The detector can also be used in combination with a Z-Wave controller for home automation uses, detecting both changes in infrared radiation levels (presence) and changes in the brightness level. Thus, we can trigger a light when detecting movement in the dark.

The detector will also raise the brightness and the temperature, i.e. in the event of a significant change, and each time a movement is detected. A Z-Wave controller (remote control, dongle…) is necessary in order to integrate this detector into your network if you already have an existing network.

## Fonctions

-   3 in 1 detector: movement, temperature, light
-   Adopts the recent Z-Wave 400series chip to support multi-channel operations and higher data throughput (9.6 / 40 / 100kbps)
-   Uses the Z-Wave 6.02 SDK
-   Optimized antenna range
-   Use for home automation or security applications
-   Button to include / exclude the detector
-   Autoprotection
-   Low battery indication
-   Small, discreet and aesthetic
-   Ease of use and installation

## Technical characteristics

-   Type of module : Z-Wave transmitter
-   Food : 1 CR123A 3V battery
-   Battery life : 2 years
-   Frequency : 868.42 MHz
-   Transmission distance : 30m indoors
-   Temperature sensor : -10 to 70 ° C
-   Brightness sensor : 0 to 500 lux
-   PIR detection angle : 90 °
-   PIR detection range : 8 to 10m
-   Dimensions : 28 x 96 x 23 mm
-   Weight : 39g
-   Operating temperature : -10 to 40 ° C
-   Operating humidity : 85% RH max
-   CE standard : EN300 220-1
-   Z-Wave certification : ZC08-13050003

## Module data

-   Mark : Philio Technology Corporation
-   Name : Philio PSP01
-   Manufacturer ID : 316
-   Product Type : 2
-   Product ID : 2

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the inclusion button 3 times, according to its paper documentation.

![inclusion](images/philio.psp01/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/philio.psp01/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/philio.psp01/commandes.jpg)

Here is the list of commands :

-   Presence : it is the command which will detect a presence detection
-   Opening : it is the command which will raise an opening detection
-   Temperature : it is the command which makes it possible to raise the temperature
-   Brightness : it is the command which makes it possible to raise the brightness
-   Sabotage : this is the sabotage command (it is triggered in the event of tearing)
-   Drums : it's the battery command

All the modules of the range having the same ids, it's up to you to display those corresponding to your module.

### Configuration of the module

> **IMPORTANT**
>
> During a first inclusion always wake up the module just after the inclusion.

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the Settings tab)

![Config1](images/philio.psp01/config1.jpg)

![Config2](images/philio.psp01/config2.jpg)

Parameter details :

-   2: sets the signal sent to the modules in association group 2
-   3: adjusts the sensitivity of the presence sensor (0 : disabled 99: max sensitivity)
-   4: adjusts the brightness level from which the signal defined in parameter 2 will be sent to the modules associated with group 2
-   5: operating mode (not recommended to change it : refer to the manufacturer's documentation)
-   6: multi-sensor operating mode (not recommended to change it : refer to the manufacturer's documentation)
-   9: allows to define after how long the OFF signal will be sent to the modules associated with group 2
-   10: allows you to define the duration between two battery reports (one unit = 30 minutes)
-   12: allows you to define the duration between two brightness reports (one unit = 30 minutes)
-   13: allows you to define the time between two temperature reports (one unit = 30 minutes)

### Groupes

This module has two association groups, only the first is essential.

![Groupe](images/philio.psp01/groupe.jpg)

## Good to know

### Specificities

> **Tip**
>
> This module has a particularity, not having a report based on variations but only on duration, it sends all its information on each detection. It also sends the presence detection signal several times in succession. It is therefore advisable to check the "Event on change" box on the presence if you use this command as a scenario trigger.

## Wakeup

To wake up this module there is only one way :

-   release the tamper button and press it again

## Important note

> **IMPORTANT**
>
> You have to wake up the module : after its inclusion, after a change in configuration, after a change in wakeup, after a change in association groups
