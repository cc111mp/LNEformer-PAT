# LNEformer-PAT

Official PyTorch implementation of:

**Local Spatial Attention Transformer for Sparse Photoacoustic Image Reconstruction**  
Simon C. K. Chan, Lulin Shi, Bingxin Huang, Terence T. W. Wong  
IEEE International Symposium on Biomedical Imaging (**ISBI**), 2024  

[Paper](https://doi.org/10.1109/ISBI56570.2024.10635699)

---

## Introduction

This repository provides the implementation of **LNEformer** for sparse photoacoustic tomography reconstruction.

LNEformer is designed to reconstruct high-quality photoacoustic images from sparse-view inputs. The model uses local neighborhood attention and a U-shaped restoration architecture to suppress undersampling artifacts and recover structural details.

<p align="center">
  <img src="assets/architecture.png" width="800">
</p>

---

## Results

Quantitative comparison on sparse PAT reconstruction.

| Method | Sparse 16 PSNR | Sparse 16 SSIM | Sparse 32 PSNR | Sparse 32 SSIM | Sparse 64 PSNR | Sparse 64 SSIM |
|---|---:|---:|---:|---:|---:|---:|
| UNet | 27.65 | 0.827 | 28.88 | 0.867 | 31.56 | 0.903 |
| NAFNet | 28.58 | 0.808 | 29.58 | 0.870 | 32.61 | 0.899 |
| Restormer | 27.92 | 0.805 | 30.11 | 0.874 | 30.92 | 0.863 |
| Shuffleformer | 28.80 | 0.842 | 29.51 | 0.865 | 32.14 | 0.900 |
| **LNEformer** | **29.39** | **0.853** | **30.74** | **0.874** | **33.17** | **0.907** |

<p align="center">
  <img src="assets/visual_comparison.png" width="800">
</p>

---

## Installation

```bash
git clone https://github.com/YOUR_USERNAME/LNEformer-PAT.git
cd LNEformer-PAT

conda create -n lneformer python=3.9 -y
conda activate lneformer

pip install -r requirements.txt
```

---

## Dataset

Please organize the dataset as follows:

```bash
data/
├── train/
│   ├── input/
│   └── target/
├── val/
│   ├── input/
│   └── target/
└── test/
    ├── input/
    └── target/
```

The sparse input images are reconstructed from 16, 32, or 64 projections.  
The target images are reconstructed from 512 projections.

---

## Training

```bash
python train.py --config configs/lneformer_16.yml
```

For other sparse settings:

```bash
python train.py --config configs/lneformer_32.yml
python train.py --config configs/lneformer_64.yml
```

---

## Testing

```bash
python test.py \
  --config configs/lneformer_16.yml \
  --checkpoint checkpoints/lneformer_16.pth
```

---

## Pretrained Models

| Model | Setting | Link |
|---|---|---|
| LNEformer | 16 projections | Coming soon |
| LNEformer | 32 projections | Coming soon |
| LNEformer | 64 projections | Coming soon |

---

## Citation

If you find this work useful, please cite:

```bibtex
@inproceedings{chan2024local,
  title={Local Spatial Attention Transformer for Sparse Photoacoustic Image Reconstruction},
  author={Chan, Simon C. K. and Shi, Lulin and Huang, Bingxin and Wong, Terence T. W.},
  booktitle={2024 IEEE International Symposium on Biomedical Imaging (ISBI)},
  year={2024},
  doi={10.1109/ISBI56570.2024.10635699}
}
