# CA2.5D-UMamba

Anonymous repository for the manuscript:

**CA2.5D-UMamba: Wavelet-Guided Center-Dominant Asymmetric Context Modeling for Multimodal Pituitary Tumor MRI Segmentation**

## Current Status

This work is currently under peer review. Author-identifying information
is omitted during double-anonymous peer review.

This repository provides experiment configurations, software environment
versions, native nnU-Net plans, and anonymous patient-level five-fold splits.
The complete implementation is scheduled for release upon publication.

## Experiment Configurations

See [the configuration documentation](reproducibility/README.md) for:

- Shared training settings: 1000 epochs per fold and random seed 12345
- Model architecture, preprocessing, inference, and evaluation settings
- The `umamba5090` software environment and comparison baseline environments
- Native nnU-Net plans, dataset metadata, and patient-level fold assignments

## Planned Code Release

The complete implementation will be made publicly available upon
publication of the paper, including:

- Model architecture and context fusion modules
- MRI preprocessing scripts
- Training and inference scripts
- Evaluation scripts
- Instructions for reproducing the experiments

## Data Availability

The clinical MRI dataset cannot be publicly released due to patient
privacy restrictions.
