# prototype
This is my first attempt at making a onehanded ergonomical mechanical keyboard. It mostly worked as expected, see [Bugs](#Bugs). 

## Folders
* Pictures of the final product are in the folder *product pictures*.
* 3D objects and corresponding gcode files for case and plate are in the folder *frame*. *Fusion 360* and *PrusaSlicer* was used to produce these.
* pcb and corresponding schematic are in the *pcb* folder. *EasyEDA* was used to produce these.

## Code
* The raspberry pi 4 was configured as a keyboard using [this](https://randomnerdtutorials.com/raspberry-pi-zero-usb-keyboard-hid/) online tutorial.
* The code was written in python and it is not appended. It was a very simple while true loop. It did not check handle *switch bounce* in any way, however this did not turn out to be a problem.

## Choice of components
* Raspberry pi 4: A small computer in and of itself, so it's definitely way stronger than needed. I used it simply because I had one at hand, and it is connected to the pcb via a flat cable so it can still be disconnected and used for other projects. A simple microcontroller such as the *Arduino Pro Micro* would be a more reasonable choice. However the microchip (ATmega32U4) has fewer gpio ports and would require me to make a standard keyboard matrix. Which would require a diode for every switch in order to avoid ghosting. It seemed simpler use a controller with more gpio ports.
* Kailh hotswap sockets: In order to make the keyboard hotswappable, such that switches easily can be changed.
* Cherry mx silver / Cherry mx red / Kailh silver: These are the different switches I used. Kailh silver and Cherry mx silver are very similar and was used interchangeably. All of them are linear switches. The silver switches has quite short pre travel, which in some cases caused misclicks on the buttons where my fingers rested. Thus I used cherry mx red on these buttons instead.
* 1k resistor in order to protect the raspberry pi from a short in the case of faulty code.

## Bugs
* Button not working properly: The button connected to GPIO 2 only works a part of the time. This is likely because of a slight oversight on my part. Both GPIO 2 and 3 are pysically connected to 1.8k unchangable pull-up resistors, which are lower values than the default. This is problematic because pressing the switch creates a connection to ground with a 1k resistor (which was added for protection). Thus it is definetely closer to logical zero but still not sufficiently close to work consistently. A possible fix is to remove or reduce the 1k resistor.

## Improvements
* Comfortable thumb buttons: The angles of the case were not the most comfortable. A big part of the problem was that pressing the thumb buttons sideways resulted in a sideways force, which resulted in displacement and/ord rotation of the keyboard. The thumb buttons could also have had angles closer to 90 degree along the xy-axis.
* Comfortable hand position: A wrist rest could be integrated into the case.
* General design: The design ended up looking very clunky and it was also very impractical to move around. The main problem is the fact that the raspberry pi 4 is connected to the keyboard via a flat cable. Adding a microchip to the pcb is the obvious solution.
