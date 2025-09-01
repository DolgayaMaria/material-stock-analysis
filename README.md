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

### 1. Municipality shapefiles
- Files: .shp, .dbf, .shx, etc.
- Coordinate system: EPSG:4326
- Required attributes:
  - kommunenum — municipality code (string, zero-padded to 4 digits)
  - kommunenav — municipality name
  - geometry — polygon geometry

### 2. Merged CSV with data
- File name: 
- Structure: One row per combination of municipality, material, energy carrier, building type and cohort.
- Required columns:
  - kommunenum (municipality code) — string, zero-padded to 4 digits
  - energy_carrier — e.g. "TOTAL", "electricity", etc.
  - material — e.g. "TOTAL", "steel", "concrete", etc.
  - type — building type (e.g. single-family house (SFH), apartment block (AB))
  - cohort — year or cohort label

---

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
- 'kommunenum' column can be renamed to match the language of the country of interest

