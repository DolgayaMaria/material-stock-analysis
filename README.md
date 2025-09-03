# Material Stock and GHG Emissions Analysis Notebooks

This repository hosts a set of Jupyter notebooks developed for the assessment and analysis of material stocks and embodied CO₂ emissions, as well as their visualization and statistical evaluation. These notebooks are designed to work together, with outputs from the **material stock and emissions assessment** forming the basis for subsequent visualization and statistical analysis. 

---

## Objectives

The objective of this repository is to provide a transparent and reproducible workflow for analyzing material stocks and associated emissions, generating plots and visualizations for communication and performing statistical analysis to support academic research and thesis work.

---

## Repository Contents

### 1. Material Stock and Emissions Assessment  
**File:** `material_stock_and_emissions_assessment.ipynb`  
- Performs the core calculations of material stocks and emissions.  
- Produces datasets that are later used for visualization and statistical analysis.  

### 2. Plotting and Visualizations  
**File:** `plotting_and_visualizations.ipynb`  
- Generates figures, charts and maps based on the outputs of the assessment notebook.  
- Provides visual material for reporting and thesis preparation.  

### 3. Statistical Analysis  
**File:** `statistical_analysis.ipynb`  
- Applies statistical methods to the results from the assessment notebook.  
- Supports data validation, interpretation and deeper analysis of trends.  

---

## Data Requirements

### For `material_stock_and_emissions_assessment.ipynb`

- **Average heated floor area per archetype dwelling**  
  *File:* `Sandberg_2017_Table_B1`  
  *Columns:* `archetype`, `average_area`  

- **Existing building stocks (residential buildings), by municipality, archetype**  
  *File:* `ssb_03175_2024_raw`  
  *Columns:* `kommunenum`, `archetype` (each per column)  

- **Dwellings, by municipality, archetype**  
  *File:* `ssb_06266_2024_full`  
  *Columns:* `kommunenum`, `archetype` (each per column)  

- **Dwellings, by municipality, other types**  
  *File:* `ssb_06266_other`  
  *Columns:* `kommunenum`, other building types (each per column)  

- **Average heated floor area per archetype building**  
  *File:* `archetypes_areas_Amini_2025_archetypes_average_area`  
  *Columns:* `archetype`, `DB_area`  

- **Average material inventory per archetype building**  
  *File:* `mi_no_updated_Amini_2025_material_inventory`  
  *Columns:* `archetype`, `material type`, `value`  

- **Dwelling manufacturing energy intensity per building type**  
  *File:* `4_EI_ManufacturingEnergyIntensity_V2.2`  
  *Columns:* `manufacturing_building_type`, `energy_carriers`, `value`  

- **Direct emission factors per energy carrier**  
  *File:* `6_PR_DirectEmissions_V1.2`  
  *Columns:* `energy_carrier`, `value`  

- **GWP100 from material production per material type**  
  *File:* `4_PE_ProcessExtensions_Materials_VN1.0`  
  *Columns:* `material_type`, `GWP100`  

---

### For `plotting_and_visualizations.ipynb`

- **Material stock per municipality, material type, archetype (kg)**  
  *File:* `material_stock_agg`  
  *Columns:* `kommunenum`, `type`, `cohort`, `material_type`, `material_stock_mean`, `material_stock_min`, `material_stock_max`, `material_stock_std`  

- **Emissions from material per municipality, material type, archetype (kg CO₂-e)**  
  *File:* `production_ms_emissions_agg`  
  *Columns:* `kommunenum`, `type`, `cohort`, `material_type`, `material_emissions_mean`, `material_emissions_min`, `material_emissions_max`, `material_emissions_std`  

- **Emissions from dwelling manufacturing per municipality, building type, energy carrier (kg CO₂-e)**  
  *File:* `manufacturing_emissions_agg`  
  *Columns:* `kommunenum`, `type`, `energy_carrier`, `manufacturing_emissions_mean`, `manufacturing_emissions_min`, `manufacturing_emissions_max`, `manufacturing_emissions_std`  

- **Total emissions per municipality, building type and cohort (kg CO₂-e)**  
  *File:* `summary_df`  
  *Columns:* `kommunenum`, `type`, `cohort`, `total_mean`, `total_std`  

- **Total heated floor area per municipality, archetype (m²)**  
  *File:* `total_heated_area_melted`  
  *Columns:* `kommunenum`, `archetype`, `total_heated_area`  

- **Shapefiles or geopackages** containing municipalities or other NUT unit masks  

- **Population per municipality**  
  *File:* `01222_20250626-164638_ssb_01222_population_2024`  
  *Columns:* `kommunenum`, `population`  

---

### For `statistical_analysis.ipynb`

- **Material stock per municipality, material type, archetype (kg)**  
  *File:* `material_stock_agg`  
  *Columns:* `kommunenum`, `type`, `cohort`, `material_type`, `material_stock_mean`, `material_stock_min`, `material_stock_max`, `material_stock_std`  

- **Total emissions per municipality, building type and cohort (kg CO₂-e)**  
  *File:* `summary_df`  
  *Columns:* `kommunenum`, `type`, `cohort`, `total_mean`, `total_std`  

- **Population per municipality**  
  *File:* `01222_20250626-164638_ssb_01222_population_2024`  
  *Columns:* `kommunenum`, `population`  

- **Urban settlements area (km²)**  
  *File:* `14216_20250825-202054_ssb_14216_urban_settlements_area_2024`  
  *Columns:* `kommunenum`, `urban_area_km2`  

- **GDP per municipality**  
  *File:* `Regional accounts, figures per inhabitant and per employed person. Regional value added is measured in basic value._ssb_gdp_counties_2024`  
  *Columns:* `kommunenum`, `GDP per inhabitant`  

- **Persons having education level per municipality**  
  *File:* `ssb_09429_2024`  
  *Columns:* `kommunenum`, `education_level` (each per column)

### 1. Municipality (or other NUTS unit) shapefiles
- Files: .shp, .dbf, .shx, etc.
- Coordinate system: EPSG:4326
- Required attributes:
  - kommunenum — municipality code (string, zero-padded to 4 digits)
  - kommunenav — municipality name
  - geometry — polygon geometry


## Prerequisites

- **Python** 3.11.5 or higher  
- **Jupyter Notebook / JupyterLab** installed  
- Install required packages:  

```bash
pip install pandas geopandas numpy matplotlib seaborn scikit-learn statsmodels adjustText
```

---

## Possible Project Folder Structure

```
your-project-root/
├── material_stock_and_emissions_assessment.ipynb   # Main analysis notebook
├── plotting_and_visualizations.ipynb              # Visualization and plotting notebook
├── statistical_analysis.ipynb                     # Statistical analysis notebook
├── data/                                         # Input datasets (place your files here)
├── outputs/                                      # (Optional) Results, figures, and tables
├── requirements.txt                              # (Optional) List of required Python packages
└── README.md                                     # Project documentation
```

---

## Usage

1. Open `material_stock_and_emissions_assessment.ipynb` and run the analysis to generate the required datasets.  
2. Use the results in `plotting_and_visualizations.ipynb` to create figures and visual material.  
3. Apply further methods in `statistical_analysis.ipynb` to evaluate and interpret the results.  

---

## Notes

- Ensure all required datasets are placed in the `/data` folder or update paths in the notebooks accordingly.
- If your files are located in different directories, update the file paths in the notebooks to match your local folder structure.
- Outputs such as processed CSVs, figures, and statistical tables can be saved in the `/outputs` folder for organization.
- 'kommunenum' and 'kommunenav' columns can be renamed to match the language of the country of interest

