# LUNGXAI: Explainable Deep Learning Framework for Lung Cancer Classification

> **A unified framework for lung cancer subtype classification from
> multi-cohort gene expression data using a 1D CNN integrated with
> Explainable AI (LIME).**



------------------------------------------------------------------------

# Overview

LUNGXAI is an end-to-end deep learning framework for multi-class lung
cancer classification using gene expression profiles collected from
multiple public repositories. The framework performs comprehensive
preprocessing, removes batch effects, balances class distributions,
trains a 1D Convolutional Neural Network (CNN), explains predictions
using LIME, and interprets biologically relevant genes through pathway
enrichment and network analysis.

The current implementation follows the workflow:

**Data Acquisition → Data Merging & Cleaning → Batch Correction &
Scaling → 1D CNN Training → Model Evaluation → LIME Explainability →
Biological Interpretation**

------------------------------------------------------------------------

# Workflow

<p align="center">
  <img src="Workflow.png" alt="LUNGXAI workflow" width="850">
</p>

**Overall workflow of LUNGXAI.** Gene expression data from GEO, TCGA, and ICGC are integrated to construct a unified dataset containing Normal, LUAD, and LUSC samples. The data undergo common-gene identification, missing-value imputation, dataset merging, duplicate removal, log2 transformation, ComBat-based batch correction, UMAP-based quality verification, Z-score normalisation, and SMOTE-based class balancing. The processed gene expression profiles are analysed using a 1D Convolutional Neural Network (CNN) with stratified 10-fold cross-validation for multi-class lung cancer classification. Model performance is assessed using multiple classification and cross-validation metrics, followed by LIME-based explainability to quantify local and fold-wise gene contributions and derive aggregated gene importance rankings. The identified genes are subsequently analysed through KEGG, GO, and Reactome pathway enrichment and gene interaction/network analysis, providing biologically interpretable insights and supporting potential biomarker discovery.

------------------------------------------------------------------------

# Features

-   Multi-source dataset integration (GEO, TCGA and ICGC)
-   Common gene identification across cohorts
-   Gene-wise median imputation
-   Batch effect correction using ComBat
-   Per-cohort log2 transformation
-   Z-score normalisation
-   UMAP verification of batch correction
-   Class balancing using SMOTE
-   1D CNN for multi-class classification
-   Stratified 10-fold cross-validation
-   LIME-based explainability
-   Gene importance aggregation across folds
-   KEGG, GO and Reactome enrichment analysis
-   Gene interaction/network analysis

------------------------------------------------------------------------

# Methodology

## 1. Data Acquisition

Gene expression datasets are collected from:

-   GEO
    -   GSE68465
    -   GSE33479
    -   GSE31210
    -   GSE30219
    -   GSE10072
    -   GSE27262
-   TCGA
    -   LUAD
    -   LUSC
-   ICGC

Target classes:

-   Normal
-   Adenocarcinoma (LUAD)
-   Squamous Cell Carcinoma (LUSC)

------------------------------------------------------------------------

## 2. Data Merging and Cleaning

The preprocessing pipeline consists of:

-   Identification of common genes
-   Gene-wise median missing value imputation
-   Dataset merging
-   Removal of duplicate genes/samples where applicable

Approximately 11,494 common genes are retained after preprocessing.

------------------------------------------------------------------------

## 3. Batch Effect Correction and Scaling

The merged dataset is processed through:

-   Per-cohort log2 transformation
-   ComBat batch effect correction
-   UMAP visualization for quality verification
-   Z-score normalization
-   SMOTE oversampling to reduce class imbalance

------------------------------------------------------------------------

## 4. Deep Learning Model

### 1D CNN

The framework employs a one-dimensional Convolutional Neural Network for
multi-class classification.

Training strategy includes:

-   Adam optimizer
-   Softmax output layer
-   Stratified 10-fold cross-validation
-   Reproducible random seed
-   Deep learning implementation in TensorFlow/Keras

------------------------------------------------------------------------

## 5. Model Evaluation

Performance is assessed using:

-   Accuracy
-   Precision
-   Recall
-   F1-score
-   ROC-AUC
-   Confusion Matrix
-   Cohen's Kappa
-   Cross-validation performance

Predictions are generated for:

-   Normal
-   Adenocarcinoma
-   Squamous Cell Carcinoma

------------------------------------------------------------------------

## 6. Explainable AI

LUNGXAI integrates Local Interpretable Model-agnostic Explanations
(LIME).

The explainability pipeline provides:

-   Local explanations for individual predictions
-   Fold-wise feature importance
-   Aggregated gene importance
-   Signed gene rankings (positive and negative contributions)

------------------------------------------------------------------------

## 7. Biological Interpretation

Important genes identified by LIME are further analysed using:

-   KEGG pathway enrichment
-   Gene Ontology (GO) enrichment
-   Reactome pathway analysis
-   Gene interaction/network analysis

This enables biological interpretation of model predictions and supports
biomarker discovery.

------------------------------------------------------------------------

# Repository Structure

``` text
LUNGXAI/
│
├── Data_merge_Combat.ipynb      # Data integration and preprocessing
├── lungxai-framework.ipynb      # Model training, evaluation and explainability
├── README.md
├── requirements.txt
└── LICENSE
```

------------------------------------------------------------------------

# Installation

``` bash
git clone https://github.com/<username>/LUNGXAI.git
cd LUNGXAI

python -m venv venv

# Windows
venv\Scripts\activate

# Linux/macOS
source venv/bin/activate

pip install -r requirements.txt
```

------------------------------------------------------------------------

# Running the Pipeline

1.  Execute **Data_merge_Combat.ipynb** to generate the harmonized
    dataset.

2.  Execute **lungxai-framework.ipynb** to:

-   Train the CNN
-   Evaluate model performance
-   Generate LIME explanations
-   Perform biological interpretation

------------------------------------------------------------------------

# Outputs

The framework produces:

-   Trained CNN model
-   Cross-validation metrics
-   Confusion matrices
-   ROC curves
-   Prediction probabilities
-   LIME explanations
-   Ranked important genes
-   Biological enrichment results
-   Gene interaction analyses

------------------------------------------------------------------------

# Applications

-   Lung cancer subtype classification
-   Explainable AI for genomics
-   Biomarker discovery
-   Precision oncology
-   Pathway analysis
-   Translational cancer research

------------------------------------------------------------------------

# Citation

If you use this repository in your research, please cite the associated
publication when available.

------------------------------------------------------------------------

# License

Distributed under the repository license.

------------------------------------------------------------------------

# Contact

**Authors**

-   Dr. Syed Naseer Ahmad Shah
-   Dr. Shaban Ahmad
-   Prof. Rafat Parveen

For research collaborations or questions, please contact the
corresponding authors.
