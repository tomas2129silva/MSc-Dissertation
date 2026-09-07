# The classification of tissue regions in SAXS imaging using unsupervised machine learning

**MSc Research Project (Biomedical Engineering)**  
**Queen Mary University of London**

## Abstract
The structural and mechanical integrity of soft connective tissues, such as skin and the articular cartilage, relies on a highly ordered extracellular matrix (ECM) that degrades during pathologies like fibrosis and osteoarthritis. While Small-Angle X-ray Scattering (SAXS) provides non-destructive biophysical feature maps of these tissues, current segmentation techniques are labour-intensive and subjective. 

This project explores whether unsupervised machine learning models can successfully cluster different tissue regions in 2D SAXS imaging. Centroid-based (K-means) and density-based (HDBSCAN) clustering algorithms are systematically evaluated on synthetic multi-zone data, unlabelled skin tissue samples, and a manually labelled cartilage dataset to quantify segmentation accuracy across different normalisation strategies, biophysical feature spaces, and pathological injury states.

## Notebooks

The repository contains four main Jupyter Notebooks:

* **`Kmeans_SAXS.ipynb`**: The initial proof of concept. Validates K-means segmentation and the impact of expanding feature dimensions on a simulated 3-zone synthetic dataset.
* **`HDBSCAN_SAXS.ipynb`**: Generates a 5-zone synthetic dataset. Tests how centroid-based algorithms (K-means) react when forced to identify incorrect cluster counts versus how density-based algorithms (HDBSCAN) autonomously discover zones and filter boundary noise.
* **`Skin_Data_Analysis.ipynb`**: Exploratory segmentation on unlabelled biological skin tissue. Includes the 4-phase morphological cleaning pipeline (binary opening, connected components, hole filling) used to remove background scatter and artifacts.
* **`Cartilage_Data_Analysis.ipynb`**: The core part of the project. Evaluates K-means and HDBSCAN against 60 manually annotated cartilage samples. This notebook contains the code for parameter/scaling optimisation, feature space comparison, and the evaluation of model accuracy across progressive pathological injury states (control, low injury, and high injury).

## Core Dependencies
* `python` (3.13.5)
* `numpy`, `pandas` (Data manipulation)
* `scikit-learn`, `hdbscan` (Machine Learning algorithms & metrics)
* `matplotlib`, `seaborn` (Data visualisation)
* `scipy` (Morphological image processing)