# Fibaro FGRWPE-101 "Wall plug"

**The module**

![module](images/fibaro.fgwpe101/module.jpg)

**The Jeedom visual**

![vuedefaut1](images/fibaro.fgwpe101/vuedefaut1.jpg)

## Summary

The Fibaro Wall Plug is a universal receiver-socket-transmitter in the form of an adapter to be plugged into a wall socket on the electrical network, compatible with the Z-Wave standard. It allows you to manage any device with a maximum power of 2.5kW, while integrating the functionality of measuring the active power of the current and the energy consumption of the devices. This module is equipped with a light ring with LEDs signaling its status and the energy consumption of any connected device. The Fibaro Wall Plug can be controlled by a button on its housing or from any controller compatible with the Z-Wave standard

## Fonctions

-   Controlled from a controller compatible with the Z-Wave standard.
-   Microchip control.
-   Execution element: Relay.
-   Measurement of active power of current and electrical energy of the receiver.

## Technical characteristics

-   Type of module : Z-Wave receiver
-   Food : 230V, 50Hz
-   Power consumption : up to 0.8W
-   Max load : 2.5kW
-   Frequency : 868.42 Mhz EU
-   Transmission distance : 50m free field, 30m indoors
-   Dimensions: 17 x 42 x 37 mm
-   Operating temperature : 0-40 ° C
-   Limit temperature : 105°C
-   Standards : LVD (2006/95 / WE), EMC (2004/108 / EC), R & TTE (1999/5 / WE)

## Module data

-   Mark : Fibar Group
-   Name : Wall Plug FGWPE-101
-   Manufacturer ID : 271
-   Product Type : 1536
-   Product ID : 4096

## Configuration

To configure the OpenZwave plugin and know how to put Jeedom in inclusion, refer to this [Documentation](https://doc.jeedom.com/en_US/plugins/automation%20protocol/openzwave/).

> **IMPORTANT**
>
> To put this module in inclusion mode, press the inclusion button 3 times, according to its paper documentation.

![inclusion](images/fibaro.fgwpe101/inclusion.jpg)

Once included you should get this :

![Plugin Zwave](images/fibaro.fgwpe101/information.jpg)

### Commandes

Once the module is recognized, the commands associated with the module will be available.

![Commands](images/fibaro.fgwpe101/commandes.jpg)

Here is the list of commands :

-   State : It is the command which allows to know the status of the socket
-   We : This is the command that turns on the outlet
-   Off : It is the command which makes it possible to extinguish the catch
-   Power : It is the command which brings up the instantaneous power consumed
-   Consumption : It is the order which reports the total consumption

Note that on the dashboard ON / OFF / STATUS commands are grouped in a single button.

### Configuration of the module

Then if you want to configure the module according to your installation, you have to go through the "Configuration" button of Jeedom's OpenZwave plugin.

![Setup plugin Zwave](images/plugin/bouton_configuration.jpg)

You will arrive on this page (after clicking on the parameters tab)

![Config1](images/fibaro.fgwpe101/config1.jpg)

![Config2](images/fibaro.fgwpe101/config2.jpg)

![Config3](images/fibaro.fgwpe101/config3.jpg)

![Config4](images/fibaro.fgwpe101/config4.jpg)

Parameter details :

-   1: allows to block the module in always ON
-   16: allows you to remember the last state in the event of a power failure
-   34: allows you to choose which type of Zwave network alarm the socket should react to
-   35: allows you to set how the outlet will respond to alarms
-   39: sets the duration of the alarm
-   40: allows you to define how much the power must vary to be raised (in%)
-   42: same as in standard mode (up to 5 times per step defined in param 43)
-   43: power rise interval
-   45: consumption rise interval (in kWh 10 = 0.1 kWh)
-   47: interval in seconds of reporting of information regardless of a variation
-   49: take into account the consumption of the module itself in the values
-   50: minimum value used by param 52
-   51: maximum value used by param 52
-   52: action to be taken if the power leaves the limits defined in parameters 50 and 51
-   60: power beyond which the plug will flash purple
-   61: color when plug is on
-   62: color when plug is off
-   63: color when a Zwave alarm is detected
-   70: safety power (the plug will cut when the power reaches this threshold)

### Groupes

This module has 3 association groups, only the third is essential.

![Groupe](images/fibaro.fgwpe101/groupe.jpg)

## Good to know

### Reset

![Config5](images/fibaro.fgwpe101/config5.jpg)

You can reset your consumption meter by clicking on this button available in the System tab. Choose PressButton.

## Wakeup

No notion of wakeup on this module.
