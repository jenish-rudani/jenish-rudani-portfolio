---
title: Beast Ultrasound Image Segmentation
summary: The objective is to apply the fundamentals learnt in ENSC895-Medical/Digital Image Processing course during my masters to design a system to automatically segment lesions in BUS images. It includes segmentation of benign and malignant tumor areas.
tags:
- Image Processing
- Matlab
date: "2022-04-19T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Final result of my Algorithm on one of the test BUS Image
  focal_point: Smart

links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/jenishrudani
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

# Abstract

Breast cancer is a global health concern for women. Therefore, detecting signs of this disease at its earlier stages is of prime importance. Using breast ultrasound images is one of the preferred  methods for diagnosing this disease due to the low energy involved in the imaging process. This project aims to develop automatic bus segmentation algorithm. To perform a fair comparison, we will use he intersection over union at the pixel level between the given ground truth and the region identified by developed algorithm between every image pair.

# Introduction

Cancer is a significant public health problem in the world today. In particular, breast cancer (BC) is one of most common types of cancer among women and biopsy is the only way to diagnose with confidence if the cancer is really present. However, ultrasound imaging is one of the most frequently used diagnostic tools to detect and classify abnormalities of the breast. In this project, we are trying to develop an Algorithm to automatically do Segmentation in Breast Ultra Sound Images. BUS Segmentation is an extremely difficult task to do especially because of three main properties of BUS Images.

- Non-Uniform distributions inside the breast lesion region.
- Ambiguous boundary due to similar appearance between lesion regions and non-lesion
backgrounds.
- Varying Irregular breast lesion shapes in BUS Images
  
Also, in addition to this we also have speckle in the BUS images, which also can affect the effectiveness of the algorithm. This makes accurate BUS segmentation a challenging and an interesting problem to solve.
