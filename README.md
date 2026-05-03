# LNEformer-PAT

Official PyTorch implementation of **LNEformer** for sparse photoacoustic tomography reconstruction.

> **Local Spatial Attention Transformer for Sparse Photoacoustic Image Reconstruction**  
> Simon C. K. Chan, Lulin Shi, Bingxin Huang, Terence T. W. Wong  
> IEEE International Symposium on Biomedical Imaging (ISBI), 2024  
> DOI: https://doi.org/10.1109/ISBI56570.2024.10635699

---

## Overview

Sparse sampling is important for fast photoacoustic tomography (PAT), but it introduces severe undersampling artifacts. **LNEformer-PAT** is a transformer-based image restoration framework designed to reconstruct high-quality PAT images from sparse-view inputs.

The model introduces a **Local Neighborhood Enhanced Transformer** design that combines:

- Neighborhood attention for spatially localized feature restoration
- Bidirectional adaptive interaction for combining convolutional local features and attention features
- A U-shaped encoder-decoder architecture for sparse artifact removal
- Charbonnier loss for image reconstruction training

<p align="center">
  <img src="assets/architecture.png" width="850">
</p>

---

## News

- `[2024.xx]` Code released.
- `[2024.xx]` Paper accepted/published at ISBI 2024.

---

## Main Results

Quantitative comparison on sparse PAT reconstruction.

| Method | Sparse 16 PSNR | Sparse 16 SSIM | Sparse 32 PSNR | Sparse 32 SSIM | Sparse 64 PSNR | Sparse 64 SSIM | Average PSNR | Average SSIM |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| UNet | 27.65 | 0.827 | 28.88 | 0.867 | 31.56 | 0.903 | 29.36 | 0.866 |
| NAFNet | 28.58 | 0.808 | 29.58 | 0.870 | 32.61 | 0.899 | 30.26 | 0.859 |
| Restormer | 27.92 | 0.805 | 30.11 | 0.874 | 30.92 | 0.863 | 29.65 | 0.847 |
| Shuffleformer | 28.80 | 0.842 | 29.51 | 0.865 | 32.14 | 0.900 | 30.15 | 0.869 |
| **LNEformer** | **29.39** | **0.853** | **30.74** | **0.874** | **33.17** | **0.907** | **31.10** | **0.878** |

<p align="center">
  <img src="assets/visual_comparison.png" width="850">
</p>

---

## Installation

```bash
git clone https://github.com/YOUR_USERNAME/LNEformer-PAT.git
cd LNEformer-PAT

conda create -n lneformer-pat python=3.9 -y
conda activate lneformer-pat

pip install -r requirements.txt
