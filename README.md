![Logo](admin/switchbot-hub.png)
# ioBroker.switchbot-hub

[![NPM version](https://img.shields.io/npm/v/iobroker.switchbot-hub.svg)](https://www.npmjs.com/package/iobroker.switchbot-hub)
[![Downloads](https://img.shields.io/npm/dm/iobroker.switchbot-hub.svg)](https://www.npmjs.com/package/iobroker.switchbot-hub)
![Number of Installations (latest)](https://iobroker.live/badges/switchbot-hub-installed.svg)
![Number of Installations (stable)](https://iobroker.live/badges/switchbot-hub-stable.svg)
[![Dependency Status](https://img.shields.io/david/DrozmotiX/iobroker.switchbot-hub.svg)](https://david-dm.org/DrozmotiX/iobroker.switchbot-hub)

[![NPM](https://nodei.co/npm/iobroker.switchbot-hub.png?downloads=true)](https://nodei.co/npm/iobroker.switchbot-hub/)

**Tests:** ![Test and Release](https://github.com/DrozmotiX/ioBroker.switchbot-hub/workflows/Test%20and%20Release/badge.svg)

## SwitchBot-hub adapter for ioBroker

This adapter allows you to control your all devices connected to your SwitchBot hub by cloud API

<span style="color:red">**** Early Alpha status at 0.0.1, only install for development/testing purposes !
</span>.

## Getting Started
Please follow these  steps to get your Open Token!
1. Download the SwitchBot app on App Store or Google Play Store
2. Register a SwitchBot account and log in into your account
3. Generate an Open Token within the app
   a) Go to Profile > Preference
   b) Tap App Version 10 times. Developer Options will show up
   c) Tap Developer Options
   d) Tap Get Token
4. Provide you token in adapter settings

### Known limitations
#### Request limit
The amount of API calls per day is limited to 1000 times, as a result of that we must limit the amount of API calls handled during one day
(1000 / 24 / 60 = 0.7 calls at max  per minute)

At adapter start we will first make 1 API call to get all devices + 1 API for each device to get all values.
If u have 5 curtains for example, the adapter start will need 6 API calls to have all data complete.

Each position/value change will require 1 API call.
To avoid reaching the limit to soon, proper intervall time must be defined during beta testing

## ToDo
[ ] Code stability & optimization
[ ] API error handling  & messages
[ ] Test all device Types, see list below
[ ] Filter states not needed in device tree
[ ] Ensure proper intervals for each device type (due to API request limit)

### Support Physical devices

| Device Type | Supported | Tested |
| ---------- | ------------ | ------------ |
| Hub | Yes | No |
| Hub Plus | Yes | No |
| Hub Mini | Yes | Yes |
| Bot (MUST enable Cloud Service first) | Yes | No |
| Curtain (MUST enable Cloud Service first) | Yes | Yes |
| Plug | Yes | No |
| Meter | Yes | No |
| Humidifier | Yes | No |
| Smart Fan | Yes | No |

### Support Virtual infrared remote devices
Virtual infrared remote devices refer to virtual devices that are used to simulate infrared signals of a home appliance remote control. A SwitchBot Hub Plus / Hub Mini is required in order to be able to create these virtual devices within the app.

Not yet implemented

[comment]: <> (| Device Type | Supported | Tested |)

[comment]: <> (| ---------- | ------------ | ------------ |)

[comment]: <> (| Air Conditioner | Yes | No |)

[comment]: <> (| TV | Yes | No |)

[comment]: <> (| Light | Yes | No |)

[comment]: <> (| IPTV/Streamer | Yes | No |)

[comment]: <> (| Set Top Box | Yes | No |)

[comment]: <> (| DVD | Yes | No |)

[comment]: <> (| Fan | Yes | No |)

[comment]: <> (| Projector | Yes | No |)

[comment]: <> (| Camera | Yes | No |)

[comment]: <> (| Air Purifier | Yes | No |)

[comment]: <> (| Speaker | Yes | No |)

[comment]: <> (| Water Heater | Yes | No |)

[comment]: <> (| Vacuum Cleaner | Yes | No |)

[comment]: <> (| Others | Yes | No |)

## Changelog
<!--
	Placeholder for the next version (at the beginning of the line):
	### **WORK IN PROGRESS**
-->

## Support me
If you like my work, please feel free to provide a personal donation  
(this is an personal Donate link for DutchmanNL, no relation to the ioBroker Project !)  
[![Donate](https://raw.githubusercontent.com/DrozmotiX/ioBroker.switchbot-hub/main/admin/button.png)](http://paypal.me/DutchmanNL)

### **WORK IN PROGRESS**
* (Dutchman) Initial alpha release, Physical devices showing/updated 
* (Dutchman) Only curtains can be controlled

## License
MIT License

Copyright (c) 2021 DutchmanNL <oss@drozmotix.eu>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.