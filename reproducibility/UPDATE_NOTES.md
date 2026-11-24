# Configuration Package Notes

## Organization

- The proposed method and its ablations share one experimental protocol and training environment.
- Model architecture and input settings are stored in `model_config.yaml`.
- Comparison baselines retain their individual environment records.
- Each fold uses 1000 training epochs and random seed 12345.
- The native plans, dataset metadata, and patient-level splits retain their original content.

## Runtime environment

- Runtime package versions follow the author-supplied `umamba5090` environment audit.
- The shared nnunetv2 version is 2.1.1.
- The package records torchaudio 2.7.1+cu128 and the Ubuntu/WSL2 platform details.
- Comparison baselines retain their individual environment records.

## File checks

- JSON and YAML syntax.
- Consistency of shared training settings and environment versions.
- Local configuration references and paths.
- Patient-level fold membership and coverage of all 97 cases.
- Byte-for-byte preservation of native plans, dataset metadata, and fold assignments.
- ZIP integrity.
