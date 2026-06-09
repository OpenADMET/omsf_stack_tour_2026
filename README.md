# OpenADMET — OMSF Conference 2026 Demo

[![Logo](https://img.shields.io/badge/OSMF-OpenADMET-%23002f4a)](https://openadmet.org/)


Demo materials for the OpenADMET presentation at the OMSF Conference 2026.

This demo covers training and fine-tuning a model for ADMET property prediction using the OpenADMET framework, as well as some analysis of the results from the recent OpenADMET ExpansionRx Challenge

## Directory structure

There are two versions of the demo notebook, targeting different hardware:

- **`01_train_and_finetune_CPU_demo/`** — intended for live presentation. Training is limited to a single epoch so the notebook runs to completion on CPU within a few minutes without requiring a GPU. Pre-computed model checkpoints are included so all prediction and analysis cells still produce meaningful results.

- **`01_train_and_finetune_GPU_full/`** — the full version for offline or GPU-equipped runs. Training runs for the complete number of epochs, producing fully converged models. This is the version used to generate the benchmark figures in `img/`.
