# CA2.5D-UMamba Experiment Configuration

The proposed method and its ablation experiments share the environment, preprocessing, training, inference, and evaluation protocol described in this package. Model architecture and input settings are stored separately. Comparison baselines have individual environment records.

## Shared settings

| Setting | Value |
| --- | --- |
| Training epochs per fold | 1000 |
| Random seed | 12345 |
| Number of folds | 5 |
| Validation patients per fold | 20, 20, 19, 19, 19 |
| Training iterations per epoch | 250 |
| Training iterations per fold | 250000 |
| Online validation iterations per epoch | 50 |
| Batch size | 12 |
| Patch size | 512 x 512 |
| Optimizer | Nesterov SGD |
| Initial learning rate | 0.01 |
| Momentum | 0.99 |
| Weight decay | 0.00003 |
| Learning-rate schedule | PolyLR, 1000 epochs, power 0.9 |
| Checkpoint selection | Maximum online foreground patch-Dice EMA |

## Environment

| Runtime setting | Value |
| --- | --- |
| Conda environment | umamba5090 |
| Operating system | Ubuntu 22.04.5 LTS |
| Virtualization | WSL2 |
| GPU | NVIDIA GeForce RTX 5090 |
| Visible GPU memory | 32607 MiB |
| NVIDIA driver | 621.14 |
| Python | 3.10.20 |
| PyTorch CUDA | 12.8 |
| CUDA Toolkit | 12.8 |
| nvcc | V12.8.93 |
| cuDNN | 9.2.0 |

| Package | Version |
| --- | --- |
| PyTorch | 2.7.1+cu128 |
| torchvision | 0.22.1+cu128 |
| torchaudio | 2.7.1+cu128 |
| nnU-Net v2 | 2.1.1 |
| mamba-ssm | 2.3.2.post1 |
| causal-conv1d | 1.6.2.post1 |
| dynamic-network-architectures | 0.4.4 |
| Triton | 3.3.1 |
| NumPy | 2.2.6 |
| SciPy | 1.15.3 |
| SimpleITK | 2.5.5 |
| batchgenerators | 0.25.3 |
| acvl-utils | 0.2.6 |
| nibabel | 5.4.2 |
| scikit-image | 0.25.2 |
| scikit-learn | 1.7.2 |
| pandas | 2.3.3 |
| einops | 0.8.2 |

Activate the runtime environment with:

```bash
conda activate umamba5090
```

`requirements.txt` lists the Python package versions. `environment.yml` stores the corresponding Conda specification. `environments/training.yaml` records the shared software environment and runtime platform.

## Files

| File | Contents |
| --- | --- |
| `experiment_config.yaml` | Shared data, preprocessing, training, inference, and evaluation settings |
| `model_config.yaml` | Proposed model architecture and input settings |
| `training_settings.yaml` | Shared training duration and random seed |
| `environment.yml` | Conda environment specification |
| `requirements.txt` | Python dependency versions |
| `configs/nnUNetPlans.json` | Native nnU-Net plans |
| `configs/dataset.json` | Modality channels, segmentation labels, and dataset metadata |
| `configs/splits_final.json` | Patient-level five-fold assignments |
| `environments/training.yaml` | Shared software environment and runtime platform |
| `environments/comparison_models.yaml` | Individual comparison baseline environments |
| `environments/efficiency.yaml` | Efficiency profiling environment and precision |
| `UPDATE_NOTES.md` | Package organization and file checks |

## Repository integration

Place `reproducibility/` in the project repository root. The shared protocol is stored in `experiment_config.yaml`. `model_config.yaml` contains the proposed model's trainer and network settings. Each ablation uses its corresponding model settings together with the shared protocol.

The project uses the native plans in `configs/nnUNetPlans.json` and the patient assignments in `configs/splits_final.json`. Training and inference run through the project custom trainers and nnU-Net pipeline on the Linux/CUDA platform.

## Dataset

The dataset contains 97 patients with T1, T1C, and T2 MRI and binary pituitary tumor labels. The fold assignments use anonymous case identifiers. The clinical dataset is held privately.
