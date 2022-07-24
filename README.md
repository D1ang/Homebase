# Homebase

Home Assistant configurations

[![Build Status](https://app.travis-ci.com/D1ang/Homebase.svg?branch=main)](https://app.travis-ci.com/D1ang/Homebase)

[![GitHub stars](https://img.shields.io/github/stars/geekofweek/homeassistant.svg?style=plasticr)](https://github.com/geekofweek/homeassistant/stargazers)
[![GitHub last commit](https://img.shields.io/github/last-commit/geekofweek/homeassistant.svg?style=plasticr)](https://github.com/geekofweek/homeassistant/commits/master)
[![HA Version](https://img.shields.io/badge/Running%20Home%20Assistant-2022.7.6%20-darkblue)](https://github.com/home-assistant/home-assistant/releases/latest)
[![HA Version](https://img.shields.io/badge/Original%20Home%20Assistant-0.14%20-darkblue)](https://github.com/home-assistant/core/releases/0.14)
[![HA Community](https://img.shields.io/badge/HA%20community-forum-orange)](https://community.home-assistant.io/u/geekoftheweek/summary)

## Overview

My [Home Assistant - VM](https://home-assistant.io) configurations with automations & settings.  These are my active automations and configurations that I use every day.  Updated frequently as I add more devices and come up with more and more automations to do simple tasks.

# <a name="menu">Menu</a>
 | [Hubs](#hubs) | [Lighting](#lighting) | [Climate](#climate)| [Outlets & Switches](#outlets)|  [Locks](#locks) | [Security](#security) | [Voice Assistant](#voice) | [Media](#media) | [Sensors](#sensors) | [Cameras](#cameras) | [Garage](#garage) | [Vacuum](#vacuum) | [Blinds](#blinds) | [Energy](#energy) | [Appliances](#appliances) | [Network](#network) | [Other Hardware](#other)| [Software](#software) | [Retired Devices](#retired)  | [Screenshots](#screenshots) |

## Hubs

| [Go to Menu](#menu) |

| Device                | Intergration  | Connection      | Home Assistant    | Notes                              |
| :-------------------- | :-----------: | :-------------- | :---------------- | ---------------------------------- |
| Conbee II             | Local         | USB  -> Zigbee  | deCONZ            | Used to control all Zigbee Devices |
| RFXtrx                | Local         | USB  -> 433 MHz | RFXcom            | Used to control all Screens        |
| Logitech Harmony Hub  | Local         | Wifi -> IR      | Homebase Hub      | Used to control IR remote devices  |
| MiLight               | Local         | Wifi -> 433 MHz | LimitlessLED      | Used to control Office spots       |

Relevant configurations can be found within [configuration.yaml](https://github.com/geekofweek/homeassistant/blob/master/configuration.yaml)

## Energy

| [Go to Menu](#menu) | [Home Screenshot](images/home-screenshot.jpg?raw=true "Home Page") |

| Device                | Intergration  | Connection    | Home Assistant    | Notes                              |
| :-------------------- | :-----------: | :------------ | :---------------- | ---------------------------------- |
| Conbee II             | Local         | USB           | deCONZ            | Used to control all Zigbee Devices |
| RFXtrx                | Local         | USB           | RFXcom            | Used to control all Screens        |
| Logitech Harmony Hub  | Local         | Wifi          | Homebase Hub      | Used to control IR remote devices  |

Many of my automations rely on some form of lighting but many examples can be found in [lights.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/lights.yaml) and [location.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/location.yaml).

Lights are grouped via [light_group.yaml](https://github.com/geekofweek/homeassistant/blob/master/light_group.yaml)

## Climate

| [Go to Menu](#menu) | [Daikin Residential Controller](https://github.com/rospogrigio/daikin_residential) |

| Device                | Intergration     | Connection    | Home Assistant     | Notes                              |
| :-------------------- | :--------------: | :------------ | :----------------- | ---------------------------------- |
| Daikin                | Depens on cloud  | Wifi          | Daikin residential | Custom component to control Airo's |

I utilize a number of automations that adjust climate controls.  Mostly they can be found in [climate.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/climate.yaml). Ecobee room sensors are heavily used in [occupancy.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/occupancy.yaml) and as conditions in many automations

More detailed information on the ESPhome configuration can be found in [here](https://github.com/geekofweek/homeassistant/tree/master/esphome/garage_door_relay)

## <a name="outlets">Outlets & Switches</a>

| [Go to Menu](#menu) | [Home Screenshot](images/home-screenshot.jpg?raw=true "Home Page") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Wemo Mini Smart Plug](https://amzn.to/2wQ05jE) | 4 | Wi-Fi | [Belkin WeMo](https://www.home-assistant.io/components/wemo/) | Smart outlets utilized to control various devices via powering the outlet on/off (fans, Christmas Tree, etc) |
| [Wemo Insight Smart Plug](https://amzn.to/2CfzHRa) | 2 | Wi-Fi | [Belkin WeMo](https://www.home-assistant.io/components/wemo/) | Smart outlet utilized to monitor power |
| [Zooz Power Switch ZEN15](https://amzn.to/2WRPeiv) | 2 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Smart outlet utilized to monitor power to sump pump |
| [GE Z-Wave Wireless Smart Lighting Control Outdoor Module](https://amzn.to/2KuFRxN) | 4 | Z-Wave| [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Used to control low voltage outdoor lighting transformers, bug zapper, and Christmas lights (Holiday time only) |
| [Remotec Zwave Dry Contact Fixture Module](https://amzn.to/2rOmcBW) | 1 | Z-Wave| [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Used to control gas fireplace |
| [Dome Home Automation Water Shut-Off Valve](https://amzn.to/2IzJR1J) | 1 | Z-Wave| [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Used to shut off Water Main Supply to House in the event of water leak detected or while on Vacation |


Switches and outlets are used in various capacities, some are for lighting and some are for fans type devices.  [lights.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/lights.yaml) and [occupancy.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/occupancy.yaml) should have some good examples.

Washing machine is automated around the Wemo Insight Plug.  This outlet can monitor power consumption, I created a [sensor](https://github.com/geekofweek/homeassistant/blob/master/sensors.yaml) based on the power reading that shows a simple status of running or not running thus [automating](https://github.com/geekofweek/homeassistant/blob/master/automation/laundry.yaml) around that sensor.

## <a name="locks">Locks</a>

| [Go to Menu](#menu) | [Alarm Screenshot](images/alarm-screenshot.jpg?raw=true "Alarm") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Schlage Connect Touchscreen Deadbolt](https://amzn.to/2KwXltd) | 3 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Smart locks used in automations to auto lock / unlock doors |

Locks are used mostly as a way to lock / unlock doors based on locations, see [location.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/location.yaml) and [locks.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/locks.yaml) for some examples

## <a name="security">Security</a>

| [Go to Menu](#menu) | [Alarm Screenshot](images/alarm-screenshot.jpg?raw=true "Alarm") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [GoControl Door/Window Sensor](https://amzn.to/2wOhLfn) | 3 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Door sensors to detect if exterior doors have been opened / closed |
| [GoControl Siren and Strobe](https://amzn.to/2k4bK4U) | 1 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Alarm used for when alarm is triggered or when you want to get someone's attention|

Door sensors, motion sensors, and the alarm siren are used in many different ways via [alarm.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/alarm.yaml).  I've also implemented some of the alarm functions as part of [water_sensors.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/water_sensors.yaml).

## <a name="voice">Voice Assistant</a>

| [Go to Menu](#menu) |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Amazon Echo](https://amzn.to/2KuPHjd) | 1 | Wi-Fi | [Home Assistant Cloud](https://www.home-assistant.io/cloud/) | Audio only Voice Assistant |
| [Amazon Echo Dot](https://amzn.to/2wSreSW) | 7 | Wi-Fi | [Home Assistant Cloud](https://www.home-assistant.io/cloud/) | Audio only Voice Assistant |
| [Amazon Echo Spot](https://amzn.to/2rOVZ6a) | 1 | Wi-Fi | [Home Assistant Cloud](https://www.home-assistant.io/cloud/) | Voice Assistant with small display |
| [Amazon Echo Show](https://amzn.to/2rRhN0n) | 1 | Wi-Fi | [Home Assistant Cloud](https://www.home-assistant.io/cloud/) |Voice Assistant with display |
| [Amazon Echo Show 5](https://amzn.to/3sPEh09) | 1 | Wi-Fi | [Home Assistant Cloud](https://www.home-assistant.io/cloud/) |Voice Assistant with display 

I go for native Echo integration wherever possible, but a few devices are not currently supported where I've had to implement some work arounds via Home Assistant Cloud (previously Emulated Hue).  Most of these are just exposed via an [input_boolean]( https://github.com/geekofweek/homeassistant/blob/master/input_boolean.yaml) and [customize.yaml]( https://github.com/geekofweek/homeassistant/blob/master/customize.yaml).  This allows the ability to have echo turn on or off an [input_boolean]( https://github.com/geekofweek/homeassistant/blob/master/input_boolean.yaml)  in turn triggering an automation.

## <a name="media">Media</a>

| [Go to Menu](#menu) | [Media Screenshot](images/media-screenshot.jpg?raw=true "Media") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Apple TV 4k](https://www.amazon.com/Apple-MQD22LL-A-TV-4K/dp/B075NCMLYL/ref=sr_1_2?ie=UTF8&qid=1526581374&sr=8-2&keywords=Apple+TV) | 4 | Wi-Fi | [Apple TV](https://www.home-assistant.io/components/apple_tv/) | Used for media playback on 4k TVs |
| [Apple TV 4](https://www.amazon.com/Apple-TV-32GB-4th-Generation/dp/B075NFX24M/ref=sr_1_1?s=electronics&ie=UTF8&qid=1526581435&sr=1-1&keywords=Apple+TV) | 2 | Wi-Fi | [Apple TV](https://www.home-assistant.io/components/apple_tv/) | Used for media playback on TVs |
| [Sonos Arc](https://amzn.to/3xb9JY1) | 1 | Ethernet |  [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | TV Soundbar for audio playback and Home Assistant TTS. |
| [Sonos Sub](https://amzn.to/3lgO5iB) | 1 | Ethernet | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Audio playback and Home Assistant TTS |
| [Sonos Play:1](https://amzn.to/2IrsIor) | 10 | Wi-Fi | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Audio playback and Home Assistant TTS |
| [Sonos One SL](https://amzn.to/37aXQqa) | 2 | Wi-Fi | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Audio playback and Home Assistant TTS |
| [Sonos Move](https://amzn.to/2mJ0mAk) | 2 | Wi-Fi | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Portable Audio playback and Home Assistant TTS |
| [Sonos Roam](https://amzn.to/3zZHU6v) | 1 | Wi-Fi | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Portable Audio playback and Home Assistant TTS |
| [Sonos Beam](https://amzn.to/3mWzhCM) | 2 | Wi-Fi | [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | TV Soundbar for Audio playback and Home Assistant TTS |
| [Sonos Port](https://amzn.to/3bnJyn8) | 1 | Ethernet |  [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Audio playback and Home Assistant TTS. Connects Sonos to existing surround sound system |
| [Sonos Connect:AMP](https://amzn.to/2rQ0XzM) | 1 | Wi-Fi |  [Sonos](https://www.home-assistant.io/components/media_player.sonos/) | Audio playback and Home Assistant TTS. Connects Sonos to outdoor speakers |
| [Lutron Caseta Pico Remote Control for Audio](https://amzn.to/2QsBtnj) | 3 | Lutron Clear Connect | [Lutron Caseta Pro](https://github.com/upsert/lutron-caseta-pro) (Custom Component) | Decora wall mountable remote. Used to control Sonos |
| [Logitech Harmony Hub](https://amzn.to/2IuEvlS) | 3 | Wi-Fi | [Harmony Hub Remote](https://www.home-assistant.io/components/remote.harmony/) | Controls various AV equipment and other devices that utilize infrared remotes |
| [Samsung QN75Q80TA](https://amzn.to/3qzvOx7) | 1 | Wi-Fi | [Samsung Smart TV](https://www.home-assistant.io/integrations/samsungtv/) | 75" 4K QLED TV |
| [LG OLED55BXPUA](https://amzn.to/36THinl) | 1 | Wi-Fi | [LG webOS Smart TV](https://www.home-assistant.io/integrations/webostv/) | 55" 4K OLED TV |
| [Plex Media Server](https://plex.tv) | 1 | Ethernet | [Plex](https://www.home-assistant.io/components/media_player.plex) / [Plex Activity Monitor](https://www.home-assistant.io/components/sensor.plex/) |  Media Server|  

Most media player based automations can be found in [media.yaml]( https://github.com/geekofweek/homeassistant/blob/master/automation/media.yaml) and some Text to Speech (TTS) based automation in various automations.

Harmony Hubs work via a combination of [input_selects]( https://github.com/geekofweek/homeassistant/blob/master/input_select.yaml), [scripts]( https://github.com/geekofweek/homeassistant/blob/master/scripts.yaml), and automations in [media.yaml]( https://github.com/geekofweek/homeassistant/blob/master/automation/media.yaml).

## <a name="sensors">Sensors</a>

| [Go to Menu](#menu) | [System Screenshot](images/system-screenshot.jpg?raw=true "System") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Nest Protect v2 Battery](https://amzn.to/2LJ0ACn) | 6 | Wi-Fi | [Nest](https://www.home-assistant.io/components/nest/) | Smoke Alarm and CO Alarm.  I realized most of my Smoke Alarms had long suprased the 10 year mark and it was time for some replacements. I usually avoid Google owned products for various reasons, but the Nest Protect line has high praise. |
| [Dome Motion Detector - Light Sensor](https://amzn.to/2W9TMDS) | 8 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Motion and Light Level sensor used to automate around motion events and current room brightness. |
| [GoControl PIR Motion Detector](https://amzn.to/2HCvyZJ) | 1 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Motion sensor used to automate around motion events. |
| [ZOOZ 4-in-1 Sensor ZSE40](https://amzn.to/3aTqGhZ) | 5 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Motion,temperature, humidity, and light level sensor used to automate around motion events. |
| [Dome Home Automation Leak Sensor](https://amzn.to/2IA5XBj) | 8 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Water sensors used to detect the pressence of water as a preventive measure |
| [Aeon Labs Water Sensor](https://amzn.to/2rM6KFE) | 2 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Water sensors used to detect the pressence of water as a preventive measure |
| [Ecolink Door/Window Sensor](https://amzn.to/3cCjhUU) | 2 | Z-Wave | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) | Trial run on Window sensors to stop my blinds from closing when a Window is Open.  Starting small but we all know how that will end up.  ALL THE WINDOWS! |
| [Flume v2](https://amzn.to/3zx6grj) | 2 | Wi-Fi | [Flume](https://www.home-assistant.io/integrations/flume/) | Monitors whole house water consumption based on water meter useage |

Water sensors serve one major function, to alert me to the presence of water.  Almost all of those automations can be fond via [water_works.yaml]( https://github.com/geekofweek/homeassistant/blob/master/automation/water_works.yaml)

Smoke detectors, like the water sensors, have one real function to alert me of smoke or CO2.  Almost all of those automations can be fond via [smoke_alarm.yaml](https://github.com/geekofweek/homeassistant/blob/master/automation/smoke_alarm.yaml)



## <a name="network">Network</a>

| [Go to Menu](#menu) | [System Screenshot](images/system-screenshot.jpg?raw=true "System") |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [Ubiquiti UniFi Cloud Key Gen2 Plus](https://amzn.to/2RUxtz1) | 1 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/) | Unifi Controller. Presence detection for non household members and devices |
| [Ubiquiti Networks Unifi Next-generation Gateway Pro (UXG-Pro-US)](https://store.ui.com/products/unifi-next-generation-gateway-professional) | 1 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/)| Primary Router. Presence detection for non household members and devices |
| [Ubiquiti Networks UniFi Switch PRO PoE - 24 Ports (USW-Pro-24-POE)](https://amzn.to/2YB8jHL) | 1 | Ethernet | [Ubiquiti Unifi WAP](https://www.home-assistant.io/components/device_tracker.unifi/)| Primary Network Switch. Presence detection for non household members and devices |
| [Ubiquiti Networks UniFi Switch - 24 Ports (US-24-250W)](https://amzn.to/2LbWLlJ) | 1 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/)| Secondary Network Switch. Presence detection for non household members and devices |
| [Ubiquiti Networks 8-Port UniFi Switch (US-8-150W)](https://amzn.to/2Iuoah9) | 2 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/)| Additional Network Switches. Presence detection for non household members and devices |
| [Ubiquiti Networks UniFi Access Point WiFi 6 Long-Range (U6-LR-US)](https://amzn.to/3cFM2yX) | 2 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/)| Wireless Access Point for interior and exterior use. Presence detection for non household members and devices. |
| [Ubiquiti Networks Unifi AP PRO (UAP-AC-PRO-US)](https://amzn.to/2rP3BFJ) | 1 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/)| Wireless Access Point for interior and exterior use. Presence detection for non household members and devices. |
| [Ubiquiti Networks Unifi Access Point WiFi 6 Lite (U6-Lite-US)](https://amzn.to/3l3Dman) | 2 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/) | Wireless Access Point for interior use. Presence detection for non household members and devices. |
| [Ubiquiti Networks Unifi Mesh AP (UAP-AC-M-US)](https://amzn.to/31QrE6E) | 1 | Ethernet | [Ubiquiti Unifi](https://www.home-assistant.io/components/device_tracker.unifi/) | Wireless Mesh Access Point for exterior use. Used in detached garage to provide internet and network traffic for cameras and devices.  Presence detection for non household members and devices. |


Since I don’t use the network equipment as my primary presence detection method most of the automation is around house guests via [house_guest.yaml]( https://github.com/geekofweek/homeassistant/blob/master/automation/house_guest.yaml).  The main function of the network equipment is to be network equipment for my fiber internet service.

## <a name="software">Software</a>

| [Go to Menu](#menu) |

| Device  | Quantity | Connection | Home Assistant | Notes |
| ------------- | :---: | ------------- | ------------- | ------------- |
| [iOS App](https://itunes.apple.com/us/app/home-assistant-open-source-home-automation/id1099568401?mt=8) | 2 | NA | [iOS](https://www.home-assistant.io/docs/ecosystem/ios/)| Used as Home Assistant interface on mobile devices and primary method of presence detection. |
| [Docker](https://www.docker.com) | 1 | Ethernet | [Installation on Docker](https://www.home-assistant.io/docs/installation/docker/) | Home Assistant install runs as a Docker Container |
| [Pi-hole](https://pi-hole.net) | 2 | Ethernet / Wi-Fi | [Pi-Hole Sensor](https://www.home-assistant.io/components/sensor.pi_hole/) | Ad blocking. Primary instance runs within a Docker container and the secondary runs on a [Raspberry-pi Zero W](https://amzn.to/2Kwcz1S) |
| [Home Assistant Management Tool](https://github.com/geekofweek/homeassistant/blob/master/tools/ha-mgmt-docker.sh) | 1 | Ethernet | NA | Custom Shell script for managing Home Assistant |

The iOS app is used for some notifications within various automations. The native iOS app is the main method of doing any location based automations via [location.yaml]( https://github.com/geekofweek/homeassistant/blob/master/automation/location.yaml) and many of the conditions I use are based on presence detection of household members.

More detailed information on the custom Home Assistant Managment Tools can be found [here](https://github.com/geekofweek/homeassistant/tree/master/tools).

# <a name="screenshots">Screenshots</a>

| [Go to Menu](#menu) |

![UI](images/home-screenshot.jpg?raw=true "Home Page")
![UI](images/living-room-screenshot.jpg?raw=true "Living Room")
![UI](images/dining-screenshot.jpg?raw=true "Dining and Kitchen")
![UI](images/bedrooms-screenshot.jpg?raw=true "Bedrooms")
![UI](images/bath-screenshot.jpg?raw=true "Bathrooms")
![UI](images/offices-screenshot.jpg?raw=true "Offices")
![UI](images/basement-screenshot.jpg?raw=true "Basement")
![UI](images/upstairs-screenshot.jpg?raw=true "Upstairs")
![UI](images/outdoor-screenshot.jpg?raw=true "Outdoors")
![UI](images/garage-screenshot.jpg?raw=true "Garage")
![UI](images/weather-screenshot.jpg?raw=true "Weather")
![UI](images/media-screenshot.jpg?raw=true "Media")
![UI](images/camera-screenshot.jpg?raw=true "Cameras")
![UI](images/location-screenshot.jpg?raw=true "Location")
![UI](images/3d-printer-screenshot.jpg?raw=true "3D Printer")
![UI](images/alarm-screenshot.jpg?raw=true "Alarm")
![UI](images/system-screenshot.jpg?raw=true "System")
![UI](images/battery-screenshot.jpg?raw=true "Battery")

| [Go to Menu](#menu) |

## Custom settings

**customize_domain.yml**
In the customize folder `asumed state` is set to `false` to remove the lighting bolts
and replace them with toggle buttons.
