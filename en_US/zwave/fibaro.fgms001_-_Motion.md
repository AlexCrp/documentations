# Fibaro Motion Sensor - FGMS-001

**The module**

![module](images/fibaro.fgms001/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/fibaro.fgms001/vuedefaut1.jpg)

## Summary

The Fibaro motion detector is a Z-Wave multifunction detector. In addition to motion detection, this device measures temperature and light intensity. This detector also has a built-in accelerometer to detect any attempt to tamper with the device.

The Fibaro motion detector is battery powered and designed to be quickly and easily installed on any surface. LED indicator signals movement, temperature level, operating mode and can be used to see if the device is in the Z-Wave network.

The motion detector can be used for lighting scenes and surveillance and / or security systems.

## Fonctions

-   Wireless motion detector
-   Detects movement using a passive infrared sensor
-   Temperature measurement
-   Light intensity measurement
-   Burglary and theft protection
-   Motion and temperature alerts signaled by flashing LED
-   Earthquake detection mode
-   Button to include / exclude the detector
-   Low battery detection
-   Very small, reduced dimensions
-   Easy installation on a wall or any other surface

## Technical characteristics

-   Type of module : Z-Wave transmitter
-   Food : CR123A 3,6VDC battery
-   Recommended height for installation : 2,4m
-   Measured temperature range : -20 ° C to 100 ° C
-   Measurement accuracy : 0,5°C
-   Brightness measurement range : 0-32000 LUX
-   Frequency : 868.42 Mhz
-   Transmission distance : 50m free field, 30m indoors
-   Dimensions: 4.4 cm in diameter
-   Operating temperature : 0-40 ° C
-   Certifications : LVD 2006/95 / WE EMC 2004/108 / WE R & TTE 1999/5 / WE RoHS II

## Module data

-   Mark : Fibar Group
-   Name : Fibaro FGMS-001 \ [Motion Sensor \]
-   Manufacturer ID : 271
-   Product Type : 2048
-   Product ID : 4097

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the inclusion button 3 times, according to its paper documentation.

![inclusion](images/fibaro.fgms001/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/fibaro.fgms001/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/fibaro.fgms001/commandes.jpg)

Here is the list of commands :

-   Presence : it is the command which will detect a presence detection
-   Temperature : it is the command which makes it possible to raise the temperature
-   Brightness : it is the command which makes it possible to raise the brightness
-   Sabotage : this is the sabotage command (it is triggered in the event of vibration)
-   Drums : it's the battery command

### Configuration of the module

> **IMPORTANT**
>
> During a first inclusion always wake up the module just after the inclusion.

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the Settings tab)

![Config1](images/fibaro.fgms001/config1.jpg)

![Config2](images/fibaro.fgms001/config2.jpg)

![Config3](images/fibaro.fgms001/config3.jpg)

![Config3](images/fibaro.fgms001/config4.jpg)

Parameter details :

-   Wakeup : this is the module wake-up interval (recommended value 7200)
-   1: adjusts the sensitivity of the presence sensor
-   2: adjusts the inertia of the presence sensor
-   3: not recommended to change this setting
-   4: not recommended to change this setting
-   6: time after which the sensor will send the "more movement" signal (recommended value 30)
-   8: activates night / day mode or both (recommended value : always active)
-   9: adjusts the threshold for switching to night mode (useful if you have changed parameter 8)
-   12: to modify only if you know why you are doing it (association with a module for example)
-   14: idem
-   16: idem
-   20: sensitivity of the gyro sensor (recommended value 15)
-   22: time after which the sensor will send the "no more sabotage" signal (recommended value 30)
-   24: lets you tell how the sabotage is notified (IMPORTANT : recommended value : Anti-sabotage sensor notified to SensorAlarm command class / Cancellation is notified after the time defined in parameter 22 )
-   26: to change only if you know why you are doing it
-   40: allows to say how much the brightness value must be modified to be sent (recommended value 50)
-   42: allows to give a minimum duration between two successive sendings even if the brightness has not changed (recommended value 3600)
-   60: allows to say how much the temperature value must be modified to be sent (recommended value 2 or 0.2 degrees)
-   62: gives the frequency of temperature measurements (recommended value 900)
-   64: allows to give a minimum duration between two successive sendings even if the temperature has not changed (recommended value 2700)
-   66: allows to adjust the temperature
-   80: allows you to choose the color of the led when there is motion detection (see deactivating it)
-   81: allows to adjust the brightness of the led
-   82: adjusts the minimum brightness threshold to set the LED to 1% (linked to parameter 81)
-   83: adjusts the maximum brightness threshold to set the LED to 100% (linked to parameter 81)
-   86: temperature below which the LED will light blue (linked to parameter 81)
-   87: temperature above which the LED will light red (linked to parameter 81)
-   89: allows the LED to flash in blue / white / red in the event of sabotage

### Groupes

This module has three association groups, only the third is essential.

![Groupe](images/fibaro.fgms001/groupe.jpg)

## Good to know

### Specificities

> **Tip**
>
> This module is very finicky on wakeup and very badly configured from the factory. It is essential to wake it up well after inclusion (several times are better than one), to configure it according to your wishes, and to wake it up well so that the config is taken into account.

### Alternative visual

![vuewidget](images/fibaro.fgms001/vuewidget.jpg)

## Wakeup

To wake up this module there is only one way :

-   press the inclusion button 3 times (the light turns blue)). Even if the light turns on, it may be necessary to do this several times in succession (2 or 3)

## Faq.

This module wakes up by pressing 3 times on its inclusion button.

This module is very finicky. It is advisable to make the inclusion as close as possible to your box and to do it several times.

This module is a battery module, the new configuration will be taken into account at the next wakeup.

## Important note

> **IMPORTANT**
>
> You have to wake up the module : after its inclusion, after a change in configuration, after a change in wakeup, after a change in association groups
