+++
author = "Adrien Chapelet"
categories = ["Sigfox", "QuickSheet"]
tags = ["Advanced", "Explanations"]
date = "2019-12-28"
description = "Sigfox advanced introduction"
featured = "sigfox.jpg"
featuredalt = "A new universe"
featuredpath = "date"
linktitle = ""
title = "What is Sigfox? (for techies)"
type = "post"

+++

## Intro
If you don't have read the previous article, it can be seen as an intro to this one, and is right [HERE](../sigfox-for-dummies).
Here, I will go more into details about what makes Sigfox technology so special and the perfect solution for some IoT needs where a frugal solution is needed.

## Frequencies
Sigfox relies on unlicensed spectrum and public frequencies, hence there is regulations to comply with and this regulations are either country or continent specific.

For example, in Europe, we have the ETSI that impose us on 868mHz a 1% duty cycle (hence the 140 messages per day limit) and a 14dBm limit.
In the US, the FCC is more tolerent so we can go up to 22dBm at 915mHz.

For instance, Sigfox have 7 Radio Configuration Zones (RCZ), depending on where you are and how the regulation is.

To switch between those frequencies, Sigfox invented Monarch, which is a technology where relevant basestations (in seaports and airports) broadcast their RCZ regularly (every 5min).

![Sigfox RCZ Map](../../img/2019/12/sigfox-rcz-map.png "Sigfox RCZ Map")

## Security
Sigfox protocol includes some mechanism and technics to have security.
It has an incremental sequence number, and a AES128 to be protected against replay attacks.

Protocol by itself can go up to 3 repeats on every message to be sure that the received message by Sigfox antennas is complete (also checking the CRC).

Sigfox antennas topology also includes a spatial density that involves the fact that in most cases, your message is received by several basestations.

Sigfox also includes frequency diversity, meaning that every message (and repeat) will be around a base frequency (for example 868MHz in Europe), but with a slight random frequency shift.

## Robustness
Sigfox have 3 major advantages in terms of efficiency:

* **UNB**: Ultra Narrow Band: power is focused on a tiny frequency band, and can more easily go through the noise
* **Frequencies and timings**: Due to frequency: up to 3 signal with random frequencies, and a temporal diversity
* **Space**: Due to antennas spatial diversity

Sigfox protocol is also highly resilient to interferers, as power is focused on a tiny bandwith (UNB intrinsic ruggedness) and stations have a spatial diversity, it can easily go beyond the noise and interferers.

![Sigfox Robustness](../../img/2019/12/sigfox-robustness.png "Sigfox Robustness")

## What makes Sigfox so special?
In a nutshell, Sigfox main advantages are:

* **Simplicity**: It is very simple to get started with rapid prototyping and later with SDK and modules (or chips if volume is enough)
* **Cost**: It is the cheapest global network, that can go down below 1$ (for some messages per day, in volume)
* **Robustness to interferences**: As said before, Sigfox network is one of the best in terms of robustness
* **High coverage**: It is the largest LPWAN network, already available in 60+ countries, and soon all over the world with satellites 


## When to use (or not) Sigfox?
Sigfox technology is tailored for what I call frugal IoT: it means that the device can transmit up to 140 messages per day with up to 12 bytes each.

Sigfox is not made to transfer kilobytes or megabytes of data in seconds or minutes, but rather to transmit some lightweight messages every day.

For example, one of the main use case is tracking, because you can track things for years for like 20€ (in volume), and optimize their use, such as in logistics and supply chain for example.