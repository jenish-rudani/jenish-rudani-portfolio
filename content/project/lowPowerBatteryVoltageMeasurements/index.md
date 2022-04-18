---
title: Ultra Low Power Battery Voltage Measurement
summary: Baremetal Firmware to read battery voltage without using external components, with ultra low power design
tags:
- Embedded Systems, Baremetal
date: "2022-04-17T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

# image:
#   caption: Photo by rawpixel on Unsplash
#   focal_point: Smart

links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/jenishrudani
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

## Introduction

The objective of this project is to write a sample code to read battery voltage in low power embedded devices. I am using Silicon Lab's Thunderboard (EFR32BG22). However, the fundamentals of the firmware design can be used for any microcontroller for any embedded dev kit. Here, Thunderboard has ARM Cortex M33 based target device, with 512 kB Flash, and 32 kB ram. 

Let's get to the point, without mentioning every little details of this board. You can get those from [here](https://www.silabs.com/development-tools/thunderboard/thunderboard-bg22-kit).

Internally, at GuardRFID, we use starter kit to design and develope the firmware for our BLE Tags. We can get access to following using `Mini Simplicity Connector`, which is really handy for debugging FW, Power Consumption etc.
- AEM
- PTI
- VCOM
- SWD

In most ultra low power embedded devices, for which the battery life estimate could range from 2 years to even 6 years, we do not have much flexibility in terms of adding additional passive/active components in the PCBA. Reason being, smaller footprints, and low cost requirements. Also, addition of these components contribute to higher power consumption. 

### `So, how do you read battery voltage without using external components?`

We utilize internal voltage reference of the SoC. Also, we have Analog to Digital(ADC) peripheral in almost every microcontroller. We can use internal VRef, and the ADC peripheral to read the connected battery voltage without the need of external components.

In ultra low power embedded systems, you would have a system tick of <`x`>. This X can range from 100 mS to 60 seconds, or more, depending upon the device and the functionality. In this project, we are going to use 10 minutes system tick. 

### `Why 10 minutes?` 

Because, generally speaking, you don't need to read battery voltage much often, as this devices have years of battery life. Whereas, if you were designing a firmware for android device, or any battery operated high power embedded device, then you would have a systick in the range of seconds. Otherwise, battery measurement is not a critical task that needs to addressed every few seconds. 

