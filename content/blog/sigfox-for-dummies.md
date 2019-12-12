+++
author = "Adrien Chapelet"
categories = ["Sigfox", "QuickSheet"]
tags = ["Beginner", "Explanations"]
date = "2019-12-12"
description = "Sigfox 101 introduction"
featured = "sig.jpg"
featuredalt = "A new universe"
featuredpath = "date"
linktitle = ""
title = "What is Sigfox? (for dummies)"
type = "post"

+++

## Introduction

Welcome to this website for our first article.

Sigfox is a 0G global network aimed to give things a voice.


### Peculiarities

Sigfox technology is now called 0G because it goes against the traditional telcos industries that goes for more speed and hence short range and high power consumption.

It is a network that allows simple (in terms of complexity), and hence cheap and long lasting devices to have a connectivity.


### Differenciators

This simplicity allows to use simple (UART communication for example) and power efficient (devices with up to 10 years of battery) components to add Sigfox radio to a device.

Sigfox technology is based on Ultra Narrow Band. It means that the energy is focused on a tiny frequency range, meaning it can easily go trough the noise and with a long range with little energy, and with an high resilience to interferences.

Sigfox is also very low cost compared to other technologies, prices varies with volume and number of messages per day but it can go from 1$ per month to few dollars per year.

With Sigfox, it is the network that is serving the device. It means that the device is sending a message in the air, and it's the network that is listening and will catch it. In a nutshell, Sigfox is a non-connected network.

Sigfox coverage is now very good, with up to 60 countries covered and many others coming, and satellites that will be launched soon to cover blind spots such as oceans...

Finally, to have a downlink (from cloud to device) capability while remaining low power, Sigfox devices are at the initiative of a Downlink message. The device sends a message and indicates at the network it will be available to receive up to 8 bytes of data just after the uplink message.


### Limitations

Unlike cellular technologies, Sigfox network relies on unlicensed network frequencies.

But unlicensed just means that you don't have to pay a fee to use it, not that you can use it no matter how you want to.
Si there is a regulation you have to comply with, and it is common to a country or a continent.

Generally you have to Listen Before Talk, a Frequency Hopping, or a 1% duty cycle.

These limitations impose a maximum messages number of 140 messages of 12 bytes from the device to the cloud (and max 4 messages of 8 bytes from the cloud to the device).