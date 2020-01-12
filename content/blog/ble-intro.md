+++
author = "Adrien Chapelet"
categories = ["BLE", "QuickSheet"]
tags = ["Beginner", "Explanations"]
date = "2020-01-11"
description = "BLE introduction"
featured = "Bluetooth_Smart_Logo.png"
featuredalt = "Smartphone communication"
featuredpath = "date"
linktitle = ""
title = "What is BLE (Bluetooth Low Energy)"
type = "post"

+++

# Protocol
The bluetooth is a short range 2.4gHz protocol aimed to be used to transfer data between a smartphone and a peripheral.

In 2006 Nokia created Wibree, that was a constrained version of bluetooth, which will later be rebranded as BLE.

BLE core concept is to use the base bluetooth radio in a frugal way, meaning that we can consume up to 10 times less if the device is emitting 10 times less.

BLE support was introduced with iPhone 4S and Galaxy S3, and is since very widespread in both high and low end smartphones.

In terms of embedded chipsets, which is for us the most interesting part, the main provider is Nordic Semi, which introduced it's nRF51 few years ago, and that is the major player in the field (about half market share), well above TI, Silabs, ST ...

## Core concepts
### Network topology
In general, BLE is used between smartphones or gateways (which acts as central devices), and things (which acts as peripheral devices). 
In this scheme, the peripheral device is broadcasting its advertising messages (containing device name, type ...), and will stop to advertise once it will be connected to a central device.

### Services
Services are one of the major concept of BLE. It allow to gather similar characreriscs under a common service.
The service can use a standard UUID for standard features such as Device Information .... Or be customized.

### GAP
GAP stands for Generic Access Profile, and it governs advertising and connections.

Rôles: device can act or as a peripheral device which is a small, low power, resource contrained device that can connect to a much more powerful central device.
It can also act as a central (like a smartphone or a tablet with a lot of processing power).

A peripheral will set a specific advertising interval, and every time this interval passes, it will retransmit it's main advertising packet. A longer delays saves power but feels less responsive if the device only advertises itself once every 2 seconds instead of every 20ms.

### GATT
GATT stands for the Generic ATTribute Profile, governs data organization and data exchanges between connected devices. One device (the peripheral) acts as a GATT Server, which stores data in Attribute records, and the second device in the connection (the central) acts as a GATT Client, requesting data from the server whenever necessary.

GATT transactions in BLE are based on high-level, nested objects called Profiles, Services and Characteristics, which can be seen in the illustration below:

![BLE Structure](../../img/2020/01/microcontrollers_GattStructure.png "BLE Structure")

#### Profile
A Profile is a simple a pre-defined collection of Services that has been compiled by either the Bluetooth SIG or by the peripheral designers.

#### Service
Services are used to break data up into logic entities, and contain specific chunks of data called characteristics. A service can have one or more characteristics, and each service distinguishes itself from other services by means of a unique numeric ID called a UUID

#### Characteristic
The lowest level concept in GATT transactions is the Characteristic, which encapsulates a single data point (though it may contain an array of related data, such as X/Y/Z values from a 3-axis accelerometer, etc.).
