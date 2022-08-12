# Homebase

[![GitHub last commit](https://img.shields.io/github/last-commit/geekofweek/homeassistant.svg?style=plasticr)](https://github.com/geekofweek/homeassistant/commits/master)
[![HA Version](https://img.shields.io/badge/Running%20Home%20Assistant-2022.7.6%20-darkblue)](https://github.com/home-assistant/home-assistant/releases/latest)
[![HA Community](https://img.shields.io/badge/HA%20community-forum-orange)](https://community.home-assistant.io/u/geekoftheweek/summary)

## Overview

My [Home Assistant - VM](https://home-assistant.io) configurations with automations & settings.  These are my active automations and configurations that I use every day.  Updated frequently as I add more devices and come up with more and more automations to do simple tasks.

### Menu

 | [Hubs](#hubs) | [Energy](#Energy) | [Climate](#Climate)|

## Hubs

| [Go to menu](#Menu) |

| Device                     | Intergration  | Connection      | Home Assistant    | Notes              |
| :------------------------- | :------------ | :-------------- | :---------------- | :----------------- |
| Sonoff ZigBee 3.0 Dongle + | Local         | USB  -> ZigBee  | Zigbee2MQtt       | All Zigbee devices |
| RFXtrx                     | Local         | USB  -> 433 MHz | RFXcom            | All screens        |
| Logitech Harmony Hub       | Local         | Wifi -> IR      | Homebase Hub      | IR remote devices  |
| MiLight                    | Local         | Wifi -> 433 MHz | LimitlessLED      | Office spots       |

Relevant configurations can be found within [configuration.yaml](https://github.com/D1ang/Homebase/blob/master/configuration.yaml)

## Energy

| [Go to Menu](#menu) | [Home Screenshot](images/home-screenshot.jpg?raw=true "Home Page") |

| Device                | Intergration     | Connection    | Home Assistant    | Notes                              |
| :-------------------- | :--------------- | :------------ | :---------------- | :--------------------------------- |
| Smart meter Gateway   | Local            | P1 -> Wifi    | DSMR reader       | Collects data from smart meter     |
| GoodWe GW3000D-NS     | Depends on cloud | Wifi          | GoodWe inverter   | Solar power inverter               |
| DSMR reader           | Local            | Wired -> MQTT | DSMR reader       | Django installation on server VM   |

Relevant configurations can be found mostly within [sensors.yaml](https://github.com/D1ang/Homebase/blob/master/devices/sensors/sensors.yaml)

Future plans are:

 - to convert the VM installation of DSMR reader to a docker based container.
 - Change the smart Gateway meter to MQTT only.
 - To change the GoodWe inverter so, that it will collect data locally see [this link](https://gitlab.com/sircuri/goodweusblogger) and removing cloud dependencie.

## Climate

| [Go to Menu](#menu) | [Daikin Residential Controller](https://github.com/rospogrigio/daikin_residential) |

| Device                | Intergration      | Connection    | Home Assistant     | Notes                              |
| :-------------------- | :---------------- | :------------ | :----------------- | ---------------------------------- |
| Daikin                | Depends on cloud  | Wifi          | Daikin residential | Custom component to control Airo's |
| Nest                  | Depends on cloud  | Wifi          | Google Nest        | Thermostat livingroom              |
| Buienradar            | Depens on cloud   | Internet      | Buienradar         | Online weather station             |

As for now no automations are build. Daikin residential is a custom intergration used for the 5 installed airco units for heat, air filtering and cooling.
Nest will be removed in the near future when we will remove the gaspipe. Buienradar for now is only used in the dashboard.

| [Go to Menu](#menu) |

## Custom settings

**customize_domain.yml**
In the customize folder `asumed state` is set to `false` to remove the lighting bolts
and replace them with toggle buttons.

EXAMPLE FOR FUTURE:
https://github.com/basnijholt/home-assistant-config
