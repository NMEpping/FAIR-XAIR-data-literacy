# FAIR-XAIR-data-literacy — DEXPI & RO-Crate tutorial

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.12+](https://img.shields.io/badge/python-3.12%2B-blue.svg)](https://www.python.org/)
[![uv](https://img.shields.io/badge/managed%20by-uv-de5fe9.svg)](https://docs.astral.sh/uv/)
[![ECIU Micromodule](https://img.shields.io/badge/ECIU-Micromodule-005b96.svg)](https://www.eciu.eu/)

> Part of an **ECIU University micromodule on FAIR & XAIR (eXplainable /
> AI-ready) data literacy**, with worked examples from **chemical and
> bioprocess engineering**.

An undergraduate-friendly tutorial for **FAIR Research Data Management (RDM)**
in **Process Systems Engineering (PSE)** using
[DEXPI](https://dexpi.org/), [pyDEXPI](https://github.com/process-intelligence-research/pyDEXPI)
and [RO-Crate](https://github.com/ResearchObject/ro-crate-py).

This repository provides two Jupyter notebooks that walk you step-by-step
through how to turn a raw P&ID file into a **machine-readable, interoperable
and reusable Research Object** that bundles plant design, sensor data and
analysis together — ready for long-term data sharing, reuse and for
training genAI models with contextualised / holistic data.

| # | Notebook | What you learn |
|---|----------|----------------|
| 1 | [notebooks/01_dexpi_fair_intro.ipynb](notebooks/01_dexpi_fair_intro.ipynb) | Why DEXPI matters for **FAIR** and **AI-ready** data, how to load a Proteus XML P&ID with `pyDEXPI`, how to inspect equipment and piping, how to build & **interactively visualize** a knowledge graph. |
| 2 | [notebooks/02_ro_crate_from_dexpi.ipynb](notebooks/02_ro_crate_from_dexpi.ipynb) | How to package and link the plant design, sensor data and analysis into a **Research Object Crate** (RO-Crate) so that other scientists (and machines!) can find, cite and reuse your work. |

---

## 1. Prerequisites

* Python ≥ 3.12
* [`uv`](https://docs.astral.sh/uv/) — the fast, modern Python package manager

Install `uv` (one-time):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## 2. Install the tutorial environment

From the repository root:

```bash
uv sync
```

This creates a virtual environment in `.venv/` and installs all dependencies
declared in [pyproject.toml](pyproject.toml), including
`pydexpi`, `networkx`, `rocrate`, `pyvis`, `rdflib`, `pandas` and JupyterLab.

## 3 Launch the notebooks

```bash
uv run jupyter lab
```

Open the [notebooks/](notebooks) folder in JupyterLab and start with
**`01_dexpi_fair_intro.ipynb`**.

> **Tip for VS Code users:** open any notebook directly and select the
> `.venv` kernel — VS Code will use the same environment that `uv sync`
> created.

## 4 What's in this repository

```
S05/
├── data/
│   ├── dexpi/                          # Sample Proteus XML P&ID (DEXPI Specification 1.3) files 
│   │   └── C01V04-VER.EX01.xml         # © DEXPI e.V.
│   └── pat_data/                       # Process Analytical Technology (PAT) data
│       └── sample_experiment.csv       # Synthetic temperature time-series
├── notebooks/
│   ├── 01_dexpi_fair_intro.ipynb       # Tutorial 1: Introduction to DEXPI & pyDEXPI
│   └── 02_ro_crate_from_dexpi.ipynb    # Tutorial 2: Introduction to RO-Crate 
├── ro_crate_output/                    # Generated RO-Crate lands here
├── pyproject.toml                      # uv-managed dependencies
└── README.md                           # This file
```

## 5 About the data

The DEXPI file [C01V04-VER.EX01.xml](data/dexpi/C01V04-VER.EX01.xml) is the
official **DEXPI 1.3 Reference P&ID** released by [DEXPI e.V.](https://dexpi.org/)
(re-distributed under their original license). It depicts a small plant with
heat exchangers, pumps, a tank and instrumentation — the perfect playground
for learning.

The synthetic [sample_experiment.csv](data/pat_data/sample_experiment.csv)
contains a temperature time-series tagged to equipment `T-101` (the tank).

## 6 License & credits

* Tutorial code: MIT License
* Sample DEXPI file: © DEXPI e.V. (see their original terms)
* `pyDEXPI` © Process Intelligence Research Group, TU Delft (AGPL-3.0)
