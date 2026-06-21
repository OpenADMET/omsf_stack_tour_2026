# OpenADMET — OMSF Stack Tour 2026

[![Logo](https://img.shields.io/badge/OSMF-OpenADMET-%23002f4a)](https://openadmet.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20604711.svg)](https://doi.org/10.5281/zenodo.20604711)

Demo materials for the **OpenADMET** session at the [OMSF Stack Tour 2026](https://events.omsf.io/) — a one-day hands-on tutorial covering the open-source tools powering modern molecular science.

**Session:** *ADMET Prediction: What & Why* — Hugo MacDermott-Opeskin, 1:30–2:15 PM

| Stop | City | Date | Venue |
|---|---|---|---|
| 01 | San Francisco | Jun 24, 2026 | Robertson Auditorium, Mission Bay Conference Center |
| 02 | Chicago | Aug 2026 | TBC |
| 03 | Boston | Oct 2026 | TBC |

## What this notebook covers

This is a hands-on walkthrough of the full OpenADMET stack using **LogD** as a worked example:

1. **Why LogD?** — scientific context: lipophilicity, its role in oral bioavailability, protein binding, and metabolic clearance, and why it is a good first endpoint to model
2. **The data problem** — why zero-shot public models fall short on program-specific chemistry, illustrated with the [ExpansionRx dataset](https://huggingface.co/spaces/openadmet/OpenADMET-ExpansionRx-Challenge)
3. **Training with Anvil** — loading curated ChEMBL data via our `data-catalogs`, configuring a CheMeleon GNN with a YAML recipe, and running `openadmet anvil`
4. **Inference** — running `openadmet predict` on a program test set and inspecting predictions and uncertainty estimates
5. **The Anvil Claude Skill** — authoring and running Anvil workflows with natural language via [openadmet-anvil-skill](https://github.com/OpenADMET/openadmet-anvil-skill)
6. **Prediction Portal** — zero-code predictions via [huggingface.co/spaces/openadmet/prediction_portal](https://huggingface.co/spaces/openadmet/prediction_portal)
7. **Internal deployment** — running the portal and models on-premise with Docker

## Directory structure

Two versions of the notebook target different hardware:

- **`01_train_and_finetune_CPU_demo/`** — for live presentation. Training is limited to a single epoch so the notebook runs to completion on CPU in a few minutes. Pre-computed model checkpoints are included so all inference and analysis cells produce meaningful results.

- **`01_train_and_finetune_GPU_full/`** — the full version for offline or GPU-equipped runs. Uses `chemeleon_logd_full.yaml` with `accelerator: gpu` and trains for up to 50 epochs with early stopping. This is the version used to generate the benchmark figures.

## Getting started

```bash
conda env create -f environment.yml
conda activate openadmet

# CPU demo (live presentation)
cd 01_train_and_finetune_CPU_demo
jupyter lab 01_train_and_finetune.ipynb

# GPU full run
cd 01_train_and_finetune_GPU_full
jupyter lab 01_train_and_finetune.ipynb
```

## Resources

| Resource | Link |
|---|---|
| OpenADMET | [openadmet.org](https://openadmet.org) |
| Documentation | [docs.openadmet.org](https://docs.openadmet.org) |
| Demos & tutorials | [demos.openadmet.org](https://demos.openadmet.org) |
| HuggingFace models | [huggingface.co/openadmet](https://huggingface.co/openadmet) |
| Prediction Portal | [huggingface.co/spaces/openadmet/prediction_portal](https://huggingface.co/spaces/openadmet/prediction_portal) |
| Anvil Claude Skill | [github.com/OpenADMET/openadmet-anvil-skill](https://github.com/OpenADMET/openadmet-anvil-skill) |
| Data catalogs | [github.com/OpenADMET/data-catalogs](https://github.com/OpenADMET/data-catalogs) |
| Optimus Prime recipes | [github.com/OpenADMET/optimus-prime](https://github.com/OpenADMET/optimus-prime) |
| OMSF Stack Tour | [events.omsf.io](https://events.omsf.io) |
