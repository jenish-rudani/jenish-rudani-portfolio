---
title: Let's build models using NVIDIA GPU
subtitle: First part in the series of Learning Edge Machine Learning

# Summary for listings and search engines
summary: This blog post provides a guide to configuring your windows 10, or Ubuntu machine so that it can build models using Tensorflow framework on Nvidia GPUs.

# Link this post with a project
projects: []

# Date published
date: "2022-04-15T00:00:00Z"

# Date updated
lastmod: "2022-04-15T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/fqZKHQkgFrY)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- Jenish Rudani

tags:
- tutorial
- ml
- gpu

categories:
- Tutorial
- Guide
---

# Installation

## Windows 10

## Preparing Python Environment
First step is to install [Anaconda](https://youtu.be/aN6OVm0mTHo) to maintain different versions of Python for various projects that you might be working on.

Now, after installing Anaconda, add `Conda` to `'Environment Path Variable'` by typing following command in `'Anaconda Powershell Prompt'`

```
conda init powershell
```

Creating new environment, and installing `tensorflow-gpu`
```
conda create --name test python=3.10
conda activate test
python -m pip install tensorflow-gpu
```

## Installing NVIDIA Cuda-Toolkit, cuDNN, Microsoft Visual C++ Compiler

Check compatibility matrix from [Tensorflow Official Website][1] and make note of compatible Python, CUDA, cuDNN version.

1. Download correct version of Cuda Toolkit from [Cuda-Toolkit Archive][2] and follow standard installation instruction.
2. Now, download the correct version of NVIDIA CUDA® Deep Neural Network library (cuDNN) from [cuDNN Archive][3] and `extract` the zip file.
3. The NVIDIA CUDA compiler `nvcc` uses a Visual C/C++ compiler behind the scenes, so we need to install compatible C/C++ compiler from [Visual C++ Archive](4).


## Integrating Cuda-Toolkit and cuDNN
Copy `bin`, `include`, `lib` directory from cuDNN directory, and paste it in `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2`

## Setting up Environmental Variables
Add following new Path Variables to `User Variable`
```
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\libnvvp
```

### Links

1. [Tensorflow-GPU Compatibility Matrix](https://www.tensorflow.org/install/source#gpu)
2. [Cuda Toolkit Archive](https://developer.nvidia.com/cuda-toolkit-archive)
3. [cuDNN Archive](https://developer.nvidia.com/rdp/cudnn-archive)
4. [CUDA / Microsoft Visual C++ compatibility](https://quasar.ugent.be/files/doc/cuda-msvc-compatibility.html)

[1]: https://www.tensorflow.org/install/source#gpu
[2]: https://developer.nvidia.com/cuda-toolkit-archive
[3]: https://developer.nvidia.com/rdp/cudnn-archive
[4]: https://quasar.ugent.be/files/doc/cuda-msvc-compatibility.html
