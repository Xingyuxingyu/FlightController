# FlightController
[![Build Status](https://travis-ci.org/ToolboxBodensee/FlightController.svg?branch=master)](https://travis-ci.org/ToolboxBodensee/FlightController)

A flight controller for the mini Talon UAV based on a Freescale FRDM K64F

## Compilation
Run


    make all

to compile the program and generate a .bin file to flash on the controller.

Run

    make flash

to copy the binary onto the dev board.

## Flight Modes
Different flight modes can be selected with 3-way switches on the
remote.

### Mode Switch (Switch 0):

| Switch Position 	| Mode            	|
|-----------------	|-----------------	|
| -100            	| Manual Mode     	|
| 0               	| Aided Mode      	|
| 100             	| Autonomous Mode 	|

### Configuration Switches (Switch 1 and 2):
Depending on the current mode the Configuration Switch serves a different purpose.

#### Manual Mode
No configuration switch is used, you have full control over the airplane.

#### Aided Mode
In Aided Mode the switches control the level of aids used. Switch 1 is used for the roll axis, Switch 2 for the pitch axis.

Modes:

| Switch Position | Mode                                             |
|-----------------|--------------------------------------------------|
| -100            | Manual Mode, no aids                             |
| 0               | Safety mode, the axis is limited to +-30 degrees |
| 100             | Level mode, the axis is always kept leveled      |

### Autonomous Mode
In Autonomous Mode the switches control the flight mode:

| Switch 1 	| Switch 2 	| Mode                                                                 	|
|----------	|----------	|----------------------------------------------------------------------	|
| -100     	| -100     	| Waypointmode: The plane follows the waypoints saved on the Nav-Board 	|
| -100     	| 0        	| Return to Home: The plane returns to the start position                  	|
| -100     	| 100      	| Keep Heading with high altitude Terrain following                    	|
| 0        	| -100     	| Landing Mode                                                         	|
| 0        	| 0        	| Launch Mode                                                          	|
| 0        	| 100      	| Stay at position                                                     	|
| 100      	| -100     	| Terrain following - low altitude                                      	|
| 100      	| 0        	| -                                                                    	|
| 100      	| 100      	| -                                                                    	|
