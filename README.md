# Rosetta

Mechanistic interpretability research on how transformer models encode concepts.

*Named for the Rosetta Stone — the same inscription in multiple scripts. These papers ask whether transformer models of different architectures encode concepts in the same geometric language.*

Four papers, three public repos.

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

## Repositories

| Repo | Purpose |
|---|---|
| [rosetta_tools](https://github.com/jamesrahenry/Rosetta_Tools) | Python library — activation extraction, CAZ metrics, Procrustes alignment, ablation, GEM construction. Install: `pip install git+https://github.com/jamesrahenry/Rosetta_Tools.git@v1.1.0` |
| [rosetta_analysis](https://github.com/jamesrahenry/Rosetta_Analysis) | Analysis scripts — all figures and tables in Papers 1–4, mapped in `PAPER_MAP.md` |
| [Rosetta_Concept_Pairs](https://github.com/jamesrahenry/Rosetta_Concept_Pairs) | Dataset — 18 concepts, 38,854 contrastive text pairs, Apache 2.0 |

---

## Reproducing results

```bash
# 1. Install the library
pip install git+https://github.com/jamesrahenry/Rosetta_Tools.git@v1.1.0

# 2. Clone analysis scripts and dataset
git clone https://github.com/jamesrahenry/Rosetta_Analysis.git
git clone https://github.com/jamesrahenry/Rosetta_Concept_Pairs.git

# 3. Run extraction, then analysis
cd Rosetta_Analysis
python extraction/extract.py             # produces ~/rosetta_data/models/
python caz/deep_dive.py                  # Paper 1 figures
python gem/build_gems.py                 # Paper 2 figures
python alignment/align_trajectory.py    # Paper 4 figures
```

See `rosetta_analysis/PAPER_MAP.md` for the exact script → figure mapping per paper.

---

James Henry · [jamesrahenry@henrynet.ca](mailto:jamesrahenry@henrynet.ca) · [ORCID 0009-0005-7126-9466](https://orcid.org/0009-0005-7126-9466)
