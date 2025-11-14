# **REGOMIX: ML-Driven Lunar Regolith Replication Using Terrestrial Oxide Mixtures**

*A Machine Learning and Optimization Framework for Sustainable Lunar ISRU Research*

## **Overview**

Lunar regolith simulants are essential for testing construction, agriculture, mobility systems, and in-situ resource utilization (ISRU) technologies on Earth before deployment on the Moon. However, conventional simulants mostly focus on **crystalline phases**, overlooking **amorphous components**, which significantly influence mechanical, thermal, and sintering behaviors of lunar soil.

This repository contains the full implementation of **REGOMIX**, a machine-learning-driven framework designed to replicate lunar regolith compositions using Earth-based geological oxide datasets. The workflow integrates **XRD**, **EDX**, **KNN imputation**, **dimensionality reduction (PCA)**, and **optimization algorithms** to identify terrestrial mixtures closely matching lunar compositions, including both crystalline *and* amorphous phases.

## **Key Features**

### **Integrated Lunar + Earth Oxide Dataset**

* Apollo, Luna, and Chang’e mission datasets
* Terrestrial analogs: Türkiye volcanic soils, JSC-1A, and published Earth simulants
* XRD + EDX laboratory measurements

### **Missing Data Imputation (KNN)**

* Handles incomplete oxide tables
* Preserves statistical consistency
* Original (missing-value) dataset also processed separately for comparison

### **Dimensionality Reduction (PCA)**

* Reduces high-dimensional oxide space
* Preserves >90% variance
* Enables clustering of Earth-lunar compositions
* Helps visualize similarity regions

### **Optimization in PCA Space**

* Determines ideal weight combinations of Earth materials
* Finds representative mixtures for lunar simulant preparation
* Identifies best-matching Earth regions (Türkiye emerged as a strong analog)

### **Validation via XRD & EDX**

* Ensures matched crystalline + amorphous phases
* Confirms fidelity of the generated mixtures

## **Repository Structure**

```
├── data/
│   ├── Lunar_raw_data.xlsx
│   ├── Earth_sample_data.xlsx
│   └── XRD_EDX_results/
│
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_knn_imputation.ipynb
│   ├── 03_pca_analysis.ipynb
│   ├── 04_clustering_visualization.ipynb
│   └── 05_optimization_algorithm.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── pca_module.py
│   ├── optimizer.py
│   └── visualization.py
│
├── results/
│   ├── PCA_plots/
│   ├── cluster_maps/
│   └── optimized_weights/
│
└── README.md
```

## **Why REGOMIX?**

Traditional lunar simulants:
 Ignore amorphous phases
 Are region-specific and not generalizable
 Lack systematic optimization

REGOMIX solves these by integrating **ML + optimization + spectroscopic validation** into a unified framework, enabling more realistic simulants for:

* Lunar construction systems
* ISRU oxygen extraction
* Thermal/mechanical testing
* Farming and microbial experiments in reduced gravity
* Planetary surface robotics


##  Technologies Used

* **Python**, NumPy, Pandas
* **scikit-learn (KNN, PCA, clustering)**
* **Matplotlib / Plotly**
* **SciPy Optimization**
* **XRD / EDX data integration**

## How to Run

```bash
git clone https://github.com/yourusername/REGOMIX.git
cd REGOMIX
pip install -r requirements.txt
jupyter notebook
```

## Future Work

* Include particle size distribution (PSD) matching
* Mechanical testing of produced simulants
* Integration with 3D printing regolith-based construction
* Biological experiments for algae/microbial growth
* Expansion to Mars simulants

## Author

**Ayush Raj**
Electrical Engineering, NIT Meghalaya
