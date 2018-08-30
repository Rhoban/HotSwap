# Hot swap

This is a simple hot swap board for dynamixel

## Features

With this system, when a battery is plugged, the LOGIC (for instance the robot computer) is powered through a diode, allowing a second battery to be plugged simultaneously

The SPDT switch allow to choose which battery is powering the motors, allowing an hot swap of the battery with the following sequence:

* Plugging the second battery
* Switching the SPDT switch
* Unplugging the first battery

The robot's computer will not reboot and the motors are now powered by the new battery

## 3 buses wiring

This Dynamixel HUB features 8 connectors, which have the same power supply but separated buses, with purpose to be combined with triple buses [Rhoban DXLBoard](http://github.com/Rhoban/DXLBoard):

* 2 connectors for leg 1
    * One should be connected to the first bus of the DXLBoard
    * The other should be connected to the first motor of one leg (the other are daisy chained)
* 4 connectors for the torso
    * One is connected to the second bus of the DXLBoard
    * The second to the first motor of left shoulder
    * The third to the first motor of right shoulder
    * The last to the first motor of the head
* 2 connectors for leg 2
    * One is connected to the second bus of DXLBoard
    * The other is connected to the other leg first mother

Then, the motors should be dispatched on three separate bus, one for left leg, one for right leg and one for the upper body of the robot.

## Components

You can find all the required components in the ``BOM.xlsx`` file. Note that you should choose between 3 and 4 pins for your dynamixel connectors.

* Switch
    * https://fr.farnell.com/arcolectric/c1520ataaa/interrupteur-a-bascule-spdt-ctr/dp/150551
    * Farnell ref: 150551
    * Constructor ref: C1520ATAAA 
* Double diode
    * https://fr.farnell.com/on-semiconductor/mbr1545ctg/diode-schottky-15a-45v-to-220/dp/1431049
    * Farnell ref: 1431049
    * Constructor ref: MBR1545CTG
* Dynamixel MOLEX connectors
    * 3 pins: https://fr.farnell.com/molex/22-03-5035/embase-droite-2-5mm-3-voies/dp/9979620
    * Farnell ref: 9979620
    * Constructor ref: 22-03-5035 
    * 4 pins: https://fr.farnell.com/molex/22035045/embase-vertical-2-5mm-4-voies/dp/1104204
    * Farnell ref: 1104204
    * Constructor ref: 22035045
