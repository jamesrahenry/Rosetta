# Rosetta

Mechanistic interpretability research on how transformer models encode concepts.

*Named for the Rosetta Stone — the same inscription in multiple scripts. These papers ask whether transformer models of different architectures encode concepts in the same geometric language.*

Four papers, three public repos.

---

## Repositories

| Repo | Purpose |
|---|---|
| [rosetta_tools](https://github.com/jamesrahenry/Rosetta_Tools) | Python library — activation extraction, CAZ metrics, Procrustes alignment, ablation, GEM construction. Install: `pip install rosetta_tools` (PyPI) or `pip install "rosetta_tools[extract,quantize]"` for GPU work |
| [rosetta_analysis](https://github.com/jamesrahenry/Rosetta_Analysis) | Analysis scripts — all figures and tables in Papers 1–4, mapped in `PAPER_MAP.md` |
| [Rosetta_Concept_Pairs](https://github.com/jamesrahenry/Rosetta_Concept_Pairs) | Dataset — 18 concepts, 38,854 contrastive text pairs, Apache 2.0 |

---

## Papers

| | Title | Description |
|---|---|---|
| 1 | [The Concept Allocation Zone: Tracking How Concepts Form Across Transformer Depth](https://arxiv.org/abs/PLACEHOLDER) | Identifies layer regions where concept separation, coherence, and velocity peak — consistently across 26 models and 7 concepts |
| 2 | [Geometric Evolution Maps: Extracting Stable Concept Probes from Transformer Residual Streams](https://arxiv.org/abs/PLACEHOLDER) | GEM nodes outperform single-layer peaks as probe extraction sites; 56.6% strict handoff wins across 17 concepts × 16 models |
| 3 | [Concept Encoding Strategies Across 26 Transformers: A Concept Allocation Zone Evaluation](https://arxiv.org/abs/PLACEHOLDER) | Validates CAZ predictions on 26 architectures; 95% causal ablation rate on gentle CAZes across 15 of 34 models |
| 4 | [Concept-Selective Convergence: Cross-Architecture Evidence for the Platonic Representation Hypothesis via Zero-PCA Procrustes Alignment](https://arxiv.org/abs/PLACEHOLDER) | Depth-stratified PRH test: Δ=+0.134, 98/98 positive, p=1.2×10⁻³⁰ across 7 concepts and multiple architecture families |

Papers 1–4 are a coordinated series. Paper 1 cites 2–4 as companions; all were developed concurrently and release together.

---

## Notebooks

Three Jupyter notebooks in [`notebooks/`](notebooks/) provide hands-on introductions — no prior familiarity with the papers required.

| Notebook | What it does | Requirements |
|----------|--------------|--------------|
| [`01_caz_framework_introduction.ipynb`](notebooks/01_caz_framework_introduction.ipynb) | Tour of the main findings across four architectures using pre-computed results from Hugging Face | CPU, no model |
| [`02_caz_interactive_demo.ipynb`](notebooks/02_caz_interactive_demo.ipynb) | Load Qwen2.5-7B (4-bit) and run CAZ on your own concept pairs | GPU ≥ 6 GB |
| [`03_caz_implementation_demo.ipynb`](notebooks/03_caz_implementation_demo.ipynb) | Implement the metrics and Procrustes alignment from scratch; reproduce the Paper 4 cross-architecture convergence result | CPU, no model |

Pre-computed results are in the [Rosetta Activations](https://huggingface.co/datasets/james-ra-henry/Rosetta-Activations) dataset on Hugging Face.

---

## Reproducing results

Each paper has a dedicated reproduce script in [rosetta_analysis](https://github.com/jamesrahenry/Rosetta_Analysis). See `PAPER_MAP.md` in that repo for the exact script → figure mapping.

```bash
git clone https://github.com/jamesrahenry/Rosetta_Analysis.git
git clone https://github.com/jamesrahenry/Rosetta_Concept_Pairs.git
cd Rosetta_Analysis
```

The reproduce scripts use `uv sync` to install all dependencies automatically (including rosetta_tools). Install [uv](https://docs.astral.sh/uv/) if not already present.

| Paper | Reproduce script |
|-------|-----------------|
| 1 — CAZ Framework | `bash scripts/reproduce_p1.sh` |
| 2 — GEM | `bash scripts/reproduce_p2.sh` |
| 3 — CAZ Validation | `bash scripts/reproduce_p3.sh` |
| 4 — PRH Convergence | `bash scripts/reproduce_p4.sh` |

All scripts read from `~/rosetta_data/` and write figures to `~/rosetta_data/results/`. Pre-extracted activations can be restored from Hugging Face — see `rosetta_analysis/README.md`.

---

James Henry · [jamesrahenry@henrynet.ca](mailto:jamesrahenry@henrynet.ca) · [ORCID 0009-0005-7126-9466](https://orcid.org/0009-0005-7126-9466)
