<p align="center">
<img src="./sbs-logo.png">
</p>

# Smart board system 
is modular system of 48mm x 48/64/80mm boards that are conected using 4 PIN connector, each SBS module are/will be equip with own low power MCU to manage periphials and communicate with supervisor

Goal of a project was to create affordable, small and modular system for home automation. By connecting multiple boards with one supervisor you can create flexible and expandable system using single bus connector

### Why?
I'm a big fan of home automation using HA/Domoticz etc. currentyl most of end devices are ESP WiFI devices with custom firmware, but i'm just tired of using and configuring X number of WIFI devices just to controll few things. Configuring, updating and minor logic changing in this modules are bit tidious, soo thats why i started this project of centralised modular and expandable system that you can put in single room, floor, garage, building to manage multiple devices.

For ex. you want to control multiple garage gate, garage lighting, and few door sensor for security, instead of buying multiple WiFi/Zigbee devices, you can use SBS sytem, by adding few relay and input modules you can achive same functionalty, and if you want to controll more things just add another module.

## Modules
| State | Name | Description | Estimate BOM per board (excl. shipping) |
| ------------- | ------------- | ------------- | ------------- |
| [D] | Relay | 4 SPDT 10A relays | 5$ |
| [D] | Digital Input | 4 optocouplers with 5-48V input range | 4$ |
| [ ] | Motor driver | Single/dual motor driver using TB67H420FTG with two impulse inputs, and relay for PSU controll | 15$ |
| [ ] | Communication bridge | Bridge between multiple communication interfaces (I2C/OneWire/RS485/CAN) | 8$ |
| [ ] | Power | Power input module with necessary power converter and safety protection, and SBUS power consumption monitoring | TBD | TBD |
| [ ] | Proto | Prototyping perfboard module | 4$ |
| [ ] | Digital Output | TBD | TBD |
| [ ] | SSR Relay | 6/8 2A SSR relays | TBD |
| [ ] | Battery | UPS battery module with charging/discharging/monitoring capabilities (possible solar charging) | TBD | TBD |
| [ ] | Analog Input | TBD | TBD |
| [ ] | Analog Output | TBD | TBD |



## Modules preview

### Relay module [SBS-RM-1.2]
![relay-module](./images/relay-module-rev12.png)

### Input module [SBS-IM-1.1]
![input-module](./images/input-module-rev11.png)
| Isolated Mode  | VIN Mode |
| ------------- | ------------- |
| ![input-module-isolated](./images/input-module-isolated.png) | ![input-module-vin](./images/input-module-vin.png) |

## WARNING 
Project is in very **EARLY STAGE** (so no file are actually present in repository)

## Standalone mode
Currently modules are equipped with ESP8285 which mean you can flash any firmware to use board as standalone WIFI enabled device

## Supervisor mode
Each board connect using bus connector with main supervisor (ESP32/RaspberryPI/PC?) using communication interface. Supervisor will be responsible for system working logic ex. if (input from module_X == high) turn relay_Y on module_Z

## Supervisor's
### Supervisor module [SBS-SV-NPI-1.0]
![input-module](./images/supervisor-nanopi-rev10.png)
This supervisor module is equipped with INA3221 voltage/current meter thus we can measure power consumption of NanoPI and each SBS Power line, also two P channel mosfet allow to cut off power for modules(in next revision this functionality will be moved to power module)

| State | Name | Description | Estimate BOM per board (excl. shipping) |
| ------------- | ------------- | ------------- | ------------- |
| [D] | NanoPi Neo | Supervisor based on NanoPi Neo 1.4 | TBD |
| [ ] | ESP32 | Supervisor based on ESP32 module | TBD |


## SBS Bus
Curently SBS bus uses JST ZH 4 pin connector, and PJON network protocol
| Row |
| ------------- |
| 24/12V |
| 5V |
| GND |
| PJON |

The connector is a debatable question, condition are as listed below 
- small footprint 
- easy to get\buy connection cables (pre made cables are cheaply available on many websites)
- high current capability (not satisfied with that JST ZH is max 1A)

until first prototype order connector type may change

## Legend
| Symbol | Meaning |
| ------------- | ------------- |
| D | Design - module are in design stage |
| P | Prototype - prototype are ordered |
| T | Testing - module are in testing phase |
| S | Software - software are developed |
| V | Victory - at least one revision of module are succesfuly developed |
|  | Awaiting development |

### Module naming schema(TBD)
SBS-[Module type]-{Optional info}-[Revision]

## LICENSE
(CC BY-NC 3.0) to be discuss!!

