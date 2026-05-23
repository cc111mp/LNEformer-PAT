# LNEformer-PAT

Official PyTorch implementation of:

**Local Spatial Attention Transformer for Sparse Photoacoustic Image Reconstruction**  
Simon C. K. Chan, Lulin Shi, Bingxin Huang, Terence T. W. Wong  
IEEE International Symposium on Biomedical Imaging (**ISBI**), 2024  

[Paper](https://doi.org/10.1109/ISBI56570.2024.10635699)

---

## Overview

**LNEformer** reconstructs sparse-view photoacoustic tomography (PAT) images with a local spatial attention transformer. The model uses local neighborhood attention and a U-shaped restoration architecture to suppress undersampling artifacts and recover structural details.

This repository is prepared as the release page for the paper implementation. Source code, configs, checkpoints, and full reproduction commands will be added with the code release.

---

## At A Glance

| Item | Description |
|---|---|
| Task | Sparse PAT image reconstruction |
| Venue | IEEE ISBI 2024, Athens, Greece |
| Inputs | Sparse-view reconstructions from 16, 32, and 64 projections |
| Targets | 512-projection reconstructions |
| Core method | Local neighborhood attention transformer |
| Metrics | PSNR / SSIM |

---

## Highlights

- Local spatial attention transformer for sparse-view PAT reconstruction.
- Sliding-window neighborhood attention for local image structure recovery.
- U-shaped image restoration architecture.
- Evaluation against UNet, NAFNet, Restormer, and Shuffleformer.

---

## Release Status

| Component | Status |
|---|---|
| Paper link | Available |
| Quantitative results | Available |
| Source code | Preparing for release |
| Environment file | Preparing for release |
| Training / testing configs | Preparing for release |
| Pretrained checkpoints | Preparing for release |
| Visual comparison figures | Preparing for release |

---

## Installation

The following setup will be used after the source code is released:

```bash
git clone https://github.com/cc111mp/LNEformer-PAT.git
cd LNEformer-PAT

conda create -n lneformer python=3.9 -y
conda activate lneformer

pip install -r requirements.txt
```

---

## Dataset

Expected data layout:

```bash
data/
|-- train/
|   |-- input/
|   `-- target/
|-- val/
|   |-- input/
|   `-- target/
`-- test/
    |-- input/
    `-- target/
```

Sparse inputs correspond to 16, 32, or 64 projection reconstructions. Targets correspond to 512-projection reconstructions.

---

## Quick Start

Example commands for the planned release:

```bash
python test.py \
  --config configs/lneformer_16.yml \
  --checkpoint checkpoints/lneformer_16.pth
```

```bash
python train.py --config configs/lneformer_16.yml
```

---

## Main Results

Quantitative comparison on sparse PAT reconstruction.

| Method | Sparse 16 PSNR | Sparse 16 SSIM | Sparse 32 PSNR | Sparse 32 SSIM | Sparse 64 PSNR | Sparse 64 SSIM |
|---|---:|---:|---:|---:|---:|---:|
| UNet | 27.65 | 0.827 | 28.88 | 0.867 | 31.56 | 0.903 |
| NAFNet | 28.58 | 0.808 | 29.58 | 0.870 | 32.61 | 0.899 |
| Restormer | 27.92 | 0.805 | 30.11 | 0.874 | 30.92 | 0.863 |
| Shuffleformer | 28.80 | 0.842 | 29.51 | 0.865 | 32.14 | 0.900 |
| **LNEformer** | **29.39** | **0.853** | **30.74** | **0.874** | **33.17** | **0.907** |

Visual comparison figures will be added with the full code release.

---

## Model Zoo

| Model | Setting | Link |
|---|---|---|
| LNEformer | 16 projections | Preparing for release |
| LNEformer | 32 projections | Preparing for release |
| LNEformer | 64 projections | Preparing for release |

---

## Release Checklist

- [x] Repository page
- [x] Paper link
- [x] Quantitative results
- [ ] Source code
- [ ] Environment file
- [ ] Training and testing configs
- [ ] Pretrained checkpoints
- [ ] Visual comparison figures

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
```

---

## Contact

For questions or updates, please open an issue in this repository.
