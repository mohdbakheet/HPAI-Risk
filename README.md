# HPAI-Risk

````markdown
# HPAI Wild-Bird Hotspots

*Spatiotemporal risk modelling of Highly Pathogenic Avian Influenza (H5) in North-American wild birds.*

---

## 1 · Quick start

```bash
# clone the lightweight repository
git clone --depth 1 https://github.com/<YOUR-USER>/hpai-hotspots.git
cd hpai-hotspots

# create the R environment (renv)  ── OR ──  use the conda file
Rscript env/install.R            # or:  conda env create -f env/environment.yml

# reproduce the sample analysis
make all                         # outputs figures into figs/
````

---

## 2 · Project goals

1. **Identify ecological hotspots** where reassortment risk is highest.
2. **Quantify viral prevalence & diversity** across migration flyways.
3. **Model transmission pathways** linking wild birds, poultry, and environment.
4. **Assess environmental & human drivers** (climate, land-use, trade).
5. **Generate predictive risk maps** to guide targeted surveillance.

---

## 3 · Repository layout

| Path           | Contents                                                      |
| -------------- | ------------------------------------------------------------- |
| `scripts/`     | R pipelines for data wrangling, modelling, and visualisation  |
| `data/sample/` | Tiny mock datasets (< 5 MB) for full reproducibility          |
| `env/`         | `install.R` (renv lock-file) **or** `environment.yml` (conda) |
| `figs/`        | Auto-generated PNG/SVG figures                                |
| `docs/`        | Extended background, data-access notes, manuscript drafts     |

---

## 4 · Key data inputs (sample run)

| Category              | Source                | Access                             |
| --------------------- | --------------------- | ---------------------------------- |
| Wild-bird occurrences | GBIF, eBird           | DOI links in `docs/data_access.md` |
| Climate (BIO01–BIO19) | WorldClim 2.1         | worldclim.org                      |
| Land-cover 100 m      | Copernicus CGLS-LC100 | see `docs/data_access.md`          |
| Livestock density     | FAO GLIMS             | “                                  |
| H5/H5N1 sequences     | GISAID / NCBI         | restricted                         |

Full provenance lives in **`docs/data_access.md`**.

---

## 5 · Analysis workflow

```mermaid
graph TD
  A[Download sample data] --> B[Pre-processing & QC]
  B --> C[Feature engineering<br>(TCI, PCA weights)]
  C --> D[Model training<br>(MaxEnt + RF ensemble)]
  D --> E[Risk mapping<br>& uncertainty]
```

---

## 6 · Results (demo)

| Figure                                | Description                                    |
| ------------------------------------- | ---------------------------------------------- |
| ![risk\_map](figs/risk_map_thumb.png) | Predicted HPAI risk 2020-2023 (Anatidae focus) |
| ![model\_perf](figs/model_perf.png)   | Five-fold CV AUC distribution (median ≈ 0.86)  |

---

## 7 · Citing this work

```bibtex
@dataset{bakheet_2025_hpai,
  author    = {Bakheet, Mohamed},
  title     = {HPAI Wild-Bird Hotspots},
  year      = {2025},
  version   = {v1.0},
  url       = {https://github.com/<YOUR-USER>/hpai-hotspots}
}
```

---

## 8 · License

Code © 2025 Mohamed Bakheet — MIT
Figures & text — CC-BY 4.0

```
```
