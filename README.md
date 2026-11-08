# Diamond (111) Confocal Raman Tomography & Dislocation Analysis

![Diamond Selected Region](../assets/diamond_selected_region.jpg)

## Overview
This repository contains an advanced computational analysis pipeline for **3D confocal Raman spectroscopy depth profiling** of diamond crystals. The project focuses on investigating the **(111) crystal facet** and characterizing subsurface lattice defects, stress fields, and dislocations within a selected $25 \times 25$ µm analytical micro-area.

The measurements were performed using a Raman spectrometer with a **785 nm laser excitation source**, capturing a 6-layer depth series ($Z = 0, -1, -2, -3, -4, -5$ µm with a 1 µm step).

---

## Repository Structure
```text
diamond-raman-tomography/
├── assets/
│   └── diamond_selected_region.jpg   # Optical micrograph of the diamond surface with selected scan region
├── data/                             # Place your .wdf Renishaw files here
├── notebooks/
│   └── diamond_raman_analysis.ipynb  # Main Jupyter notebook with data processing & 3D visualization
├── requirements.txt                  # Python dependencies
└── README.md                         # Project documentation
```

---

## Features & Methodology
1. **Renishaw WDF Data Ingestion:** Direct parsing of depth-resolved multi-layer mapping files.
2. **Curve Fitting & Parameter Extraction:** Lorentzian peak fitting around the primary diamond Raman line (~1332 cm⁻¹) to extract:
   - **Peak Intensity** (crystallinity / scattering efficiency)
   - **Peak Center Position** (residual mechanical stress & strain)
   - **FWHM Width** (defect density & phonon lifetime)
3. **Tomographic & Volumetric Visualization:**
   - XZ and YZ tomographic cross-sections (OCT-style volumetric inspection)
   - Maximum Intensity Projections (MIP) across spatial and depth dimensions
   - 3D point cloud rendering of subsurface defect structures

---

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Mike-Snegerev/diamond-raman-tomography.git
cd diamond-raman-tomography
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Add Data & Image
- Place your `.wdf` raw data files inside the `data/` directory.
- Place your optical micrograph image of the diamond facet (named `diamond_selected_region.jpg`) inside the `assets/` directory.

### 4. Run the Jupyter Notebook
```bash
jupyter notebook notebooks/diamond_raman_analysis.ipynb
```

---

## Requirements
- Python 3.10+
- NumPy, SciPy, Matplotlib, PySide6, renishawWiRE
