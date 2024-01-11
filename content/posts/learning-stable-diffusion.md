---
title: "Learning Stable Diffusion"
date: 2023-07-27
draft: true
tags: ["technology"]
---

Research and pick Stable Diffusion because open source with pretty outputs

Find repo: https://github.com/CompVis/stable-diffusion
Clone stable diffusion
```sh
git clone https://github.com/CompVis/stable-diffusion.git
cd stable-diffusion
```

Install conda by downloading [Miniconda](https://docs.conda.io/en/latest/miniconda.html) pkg
Check with
```sh
conda --version
```

Follow instructions to create environment
```sh
conda env create -f environment.yaml
conda activate ldm
```
Stuck here because cudatoolkit needs version 11.3, but Nvidia stopped supporting for Mac at 9.0