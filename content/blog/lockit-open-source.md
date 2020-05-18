+++
author = "Adrien Chapelet"
categories = ["Sigfox", "Monarch", "Tutorial"]
tags = ["Advanced", "Explanations"]
date = "2020-05-18"
description = "How to build a worldwide Sigfox device for less than 25$"
featured = "open_source_0G_tracker_low_2.jpg"
featuredalt = "Open source 0G tracker"
featuredpath = "date"
linktitle = ""
title = "Worldwide Sigfox open-source device"
type = "post"

+++

### Disclaimer

The device shown in this article is not completely worldwide (it can handle 3 Sigfox radio zones).
To make it worldwide and Monarch compatible, you just have to switch the module for the LiteOn WSG309s.


## Introduction

Welcome to this first tutorial, to build a low cost global tracker.


### Goals

The goal of this project is to build a device able to be geolocalized worldwide.

The application would be to be embedded as a powerbank in a bag or in a luggage, or just as a tracker in a wallet or a keychain.

In our pandemic times, it could also be used as a tracker that can detect surroundings bluetooth phone IDs and transmit it to the cloud (through Sigfox 0G network).


### Components
| Function | Module | Component | Price | Link |
|-|-|-|-|-|
| BLE Module | Ebyte E73-2G4M04S1B | nRF52832 | 3.30$ | https://fr.aliexpress.com/item/32974664063.html |
| Sigfox Module | LiteOn WSG303s | STM32 + S2LP | 15$ | http://www.ifroglab.com/en/?product=liteon-wsg303s-sigfox-verified-module-rc1 |
| Wifi Module | ESP-12F | ESP8266 | 1.79$ | https://fr.aliexpress.com/item/2037396994.html |
| Temperature + Humidity + Pressure | | BME280 | 2.52$ | https://fr.aliexpress.com/item/32849462236.html |
| Accelerometer | | LIS2DS12 | 4,15$ | https://fr.aliexpress.com/item/32830895610.html |

As you can see, more than 50% of the price is composed by the Sigfox module, but you can go down to about 5$ for it while ordering them in quantity.

### Programming

To program each module, you can use the TagConnect port next to each module.

### Sources

You can find a detailed tutorial on [Hackster](https://www.hackster.io/adriot/open-source-0g-tracker-296654)

Here is the firmware [sources](https://github.com/FlineIoT/firmware)

Here is the hardware [sources](https://github.com/FlineIoT/hardware)

### Acknowledgments

Fabian Lapotre: [Gitlab](https://gitlab.com/fabianlapotre) for his help with the hardware design

Cyril Fougeray: [Gitlab](https://gitlab.com/cyril.fougeray) [Github](https://github.com/fouge) for his help with the firmware development

Jose Marcelino: [Github](https://github.com/jmarcelino) for his help with module sourcing