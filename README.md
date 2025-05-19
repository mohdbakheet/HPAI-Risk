# Highly Pathogenic Avian Influenza in Wild Birds Hotspots

##  Project Overview
Wild birds, especially waterfowl, act as natural reservoirs of avian influenza viruses. Their migratory behavior and congregation at ecological hotspots contribute to the evolution and global dissemination of viruses such as HPAI H5. This repository addresses ecological, environmental, and socio-economic factors influencing HPAI spread and provides tools for niche modeling and risk mapping.

##  Project Objectives
- **Ecological Hotspots Identification**: Locate regions where virus transmission and reassortment are highly probable.
- **Viral Prevalence Assessment**: Catalog subtypes, genotypes, and viral diversity in wild birds.
- **Transmission Pathway Mapping**: Understand how HPAI spreads among wild birds, poultry, and mammals.
- **Environmental & Anthropogenic Influence**: Assess climate change, land use, and human activity impacts.
- **Predictive Modeling**: Build models integrating biological, environmental, and socio-economic data.

##  Data Sources
### Virus Data
- Host species, subtype, location, and year.

### Bird & Environmental Data
- Habitat, land use, climate variables, water bodies.

### Economic & Demographic Data
- Livestock, GDP, trade routes, population density.

### Notable Data Repositories
| Resource | Source | Link |
|---------|--------|------|
| Bird Distribution | GBIF, eBird | [GBIF](https://www.gbif.org), [eBird](https://ebird.org) |
| Climate | WorldClim | [WorldClim](https://www.worldclim.org) |
| Land Cover | MODIS/CEC/WRF | [MODIS](https://rspatialdata.github.io/land_cover.html) |
| Water Bodies | CLMS | [CLMS](https://land.copernicus.eu/) |
| Elevation | EarthEnv | [EarthEnv](http://www.earthenv.org/) |
| Livestock | FAO | [FAO](http://www.fao.org/livestock-systems/en/) |
| Population | WorldPop | [WorldPop](https://www.worldpop.org/) |
| GDP | SEDAC | [SEDAC](https://sedac.ciesin.columbia.edu/) |
| Flyways | USFWS | [Flyways](https://iris.fws.gov/APPS/ServCat/Reference/Profile/42276) |
| HPAI Cases | FAO EMPRES-i | [FAO EMPRES-i](https://empres-i.apps.fao.org/) |

## 🛠 Workflow
### Step 1: Data Collection
- Wild bird occurrence and migration.
- Domestic livestock distribution.
- Human and environmental variables.

### Step 2: Spatial Modeling
- GIS Integration.
- Machine Learning (MaxEnt, Random Forests).
- Habitat suitability mapping.

### Step 3: Risk Factor Analysis
- Landscape change, climate shifts, water body presence.

### Step 4: Predictive Mapping
- Kernel density, hotspot analysis, remote sensing tools.

### Step 5: Mitigation Strategy
- Surveillance prioritization, habitat restoration, biosecurity.

## 🧠 Advanced Modeling Components
### 1. Improved Data Quality
- Higher resolution inputs (Sentinel-2, WorldClim).

### 2. Temporal Dynamics
- Seasonal and time-series analysis (MODIS/VIIRS).

### 3. Model Refinement
- Ensemble ML, SHAP for interpretation.

### 4. Validation
- Use outbreak history and field surveys.

### 5. Socio-Economic Layers
- Trade routes, live animal markets, VIIRS nightlights.

### 6. Visualization Tools
- Web maps via Leaflet or Google Earth Engine.

### 7. Climate Scenario Forecasting
- SSP2-RCP4.5 simulations, extreme event modeling.

### 8. Multidisciplinary Collaboration
- Integration with genomic epidemiology and community data.

## 🧪 Risk Index Development
### PCA-Based Weight Derivation
- Raster stacking of species richness, population, poultry, cattle.
- PCA on aligned rasters to derive variable weights.
- Normalize absolute loadings for composite risk index.

### Example Weighting Result:
| Variable | Normalized Weight |
|---------|-------------------|
| Richness | 0.3256 |
| Population | 0.1564 |
| Poultry | 0.2068 |
| Cattle | 0.3112 |

## 📈 ROC and Threshold Analysis
- Stratified background point sampling.
- Buffer zones to reduce spatial autocorrelation.
- Breakpoint analysis, decision trees, clustering.
- ROC curve analysis for optimal thresholding.

## 🔍 Pseudo-Absence Sampling Techniques
1. **Environmental Constraint-Based**
2. **Distance-Based Sampling**
3. **Habitat Suitability Models**
4. **Expert-Knowledge Constraints**
5. **Hybrid Approaches**

## 🖥 R Scripts
- `PCA_Risk_Index.R`: Runs raster alignment, PCA, and weighting.
- `ROC_Analysis.R`: Performs ROC AUC evaluations.
- `Thresholding.R`: Uses statistical and ML-based thresholding.

## 📊 Preliminary Results
Visualizations stored in `figs/` and `fig2/` illustrate model results:
- Species richness maps
- Monthly trend plots
- Risk index heatmaps
- Moran’s I spatial analysis

## 🔧 Recommended Tools
- R (v4.3.1+)
- Packages: `terra`, `ggplot2`, `pROC`, `segmented`, `randomForest`, `caret`, `sf`, `dplyr`, `tidyterra`, `cowplot`

## 📁 Directory Structure (Suggested)
```
HPAI-Risk-Assessment/
├── data/
│   ├── bird_data/
│   ├── environmental/
│   └── economic/
├── scripts/
│   ├── PCA_Risk_Index.R
│   ├── ROC_Analysis.R
│   ├── Thresholding.R
├── figs/
├── fig2/
├── output/
└── README.md
```

## 🔗 Get Started
1. Clone the repo: `git clone https://github.com/mohdbakheet/HPAI-Risk-Assessment.git`
2. Install required packages.
3. Execute scripts in the correct order under `scripts/`.
4. Explore results in `figs/`, `fig2/`, and `output/` folders.
