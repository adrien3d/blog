+++
author = "Adrien Chapelet"
categories = ["Sigfox", "QuickSheet"]
tags = ["Beginner", "Explanations"]
date = "2020-01-12"
description = "Monarch introduction"
featured = "monarch-cover.jpg"
featuredalt = "Worldwide network"
featuredpath = "date"
linktitle = ""
title = "What is Sigfox Monarch?"
type = "post"

+++

# Introduction
This article will be about Sigfox Monarch, or how to build a global network when regulations are not global.

As you may know, Sigfox technology relies on public frequencies. Because these frequencies are public (meaning license free), there is regulations around their use.
However, the regulation on ISM band is country or continent related, and frequencies, maximum transmission power, data rate and limitations are different.

## Sigfox RCZ
![Sigfox RCZ Table](../../img/2020/01/sigfox-rcz-table.png "Sigfox RCZ Table")

For example, in Europe we can use up to 16dBm at 868 MHz with a 1% duty-cycle limit (and hence up to 140 messages per day), whereas you can use up to 24dBm (6 times more !) at 902 MHz with a Frequency hopping. 

For some years, one of Sigfox obstacle to have global objects was country regulations in terms of frequencies and spectrum occumpancy limitations.

For instance, Sigfox have 7 Radio Configuration Zones (RCZ), depending on where you are and how the regulation is.

![Sigfox RCZ Map](../../img/2019/12/sigfox-rcz-map.png "Sigfox RCZ Map")

Like most of new Sigfox technologies, Monarch was carried by a company project. For this one it was LVMH Echo tracker.
Louis Vuitton project goal was to have an autonomous (low power) global tracker that is able to track your luggage wherever you go.

So Sigfox invented Monarch, which is basically a technology where relevant basestations (in seaports and airports) broadcast their RCZ regularly (every 5min).

These base stations emits a peculiar signal (OOK modulation), with 2 patterns (first one of 362ms and second one of 38ms), where the combinaison of base frequency, and timing of the 2 patterns allows to distinguish the different radio zones even if their base frequency is about the same (for RC3, 4 and 5).

## Device side
How to be Monarch compatible?

To be Monarch compatible, you need 4 things:

- A multiband antenna

- A Power Amplifier to be able to go up to 22dBm

- A compatible chip, Monarch able

- The Monarch library for the MCU

Currently, the most popular solution is the ST S2LP transceiver that is pretty cheap and have a very optimized power consumption.
In terms of modules, you have a lot of solutions that are generally based on BlueNRG-2 + S2LP, from LiteOn, Jorjin, SeongJi....

Most popular one is LiteOn module, and you can prototype a Sigfox Monarch device with the [UnaMKR](https://www.unabiz.com/solutions/unamkr/) and the UnaMKR mini.

## Monarch scanning
What is the best Monarch scanning strategy?

Because Monarch scanning is a reception window, it can consume some battery, especially If you are waiting a few minutes every time.

Generally speaking, there is 2 tricks to do an efficient Monarch scanning:

- First one is about timing, normally Sigfox Monarch emits from 0h2min30sec and every 5min with a 10s random slot, so with your infernal clock, you must scan just before it.
![Sigfox RCZ Map](../../img/2020/01/Monarch-5-minutes-beacon.png "Sigfox Monarch beacos")

- Second one is when to do the Monarch scan, it is basically when your plane is landing or your goods are leaving the boat.
To detect those, you must use a pressure sensor to detect variations that indicate a change in terms of altitude.