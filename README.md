# LUNGXAI: A Deep Learning Framework with Explainable AI for Lung Cancer Classification from Gene Expression Data

LUNGXAI is a deep-learning framework integrating a 1D Convolutional Neural Network (CNN) with Local Interpretable Model-agnostic Explanations (LIME) for accurate and interpretable multi-class lung cancer classification from high-dimensional gene expression data. By combining predictive power with transparency, LUNGXAI bridges the gap between AI-driven genomics and clinically actionable insights.

---

##  Key Features

- **1D CNN Architecture**: Two convolutional layers, one fully connected layer, 64 filters, and dropout of 0.5 — purpose-built for high-dimensional gene expression sequences.
- **Explainability via LIME**: Integrates LIME to return softmax probabilities and identify key contributing genes, enabling biological interpretation of model decisions.
- **High Accuracy**: Achieves **98.8% accuracy** and high AUC-ROC scores in multi-class classification, outperforming traditional ML baselines (SVM, LR, NB, KNN).
- **Multi-Source Dataset**: Trained on a self-created expression dataset merged from GEO, TCGA, and ICGC repositories.
- **Biomarker Discovery**: Identifies influential genes (e.g., APP, TAF13, DNMT3B with positive influence; CDH6, FBXO46, MAVS with negative influence) to support pathway and network analysis.
- **Clinical Relevance**: Designed to support early detection, treatment guidance, and cancer genomics research.

---

##  Model Architecture

| Component             | Details                                      |
|-----------------------|----------------------------------------------|
| Model Type            | 1D Convolutional Neural Network (CNN)        |
| Convolutional Layers  | 2                                            |
| Fully Connected Layer | 1                                            |
| Filters               | 64                                           |
| Dropout               | 0.5                                          |
| Optimiser             | Adam (lr = 0.001)                           |
| Batch Size            | 64                                           |
| Early Stopping        | Over 50 epochs                               |
| Output                | Softmax probabilities (multi-class)          |
| Explainability        | LIME (Local Interpretable Model-agnostic Explanations) |

---

## 📊 Dataset

LUNGXAI is trained on a **self-created, merged gene expression dataset** compiled from multiple public repositories:

| Source        | Accessions / Cohorts                                            |
|---------------|-----------------------------------------------------------------|
| GEO           | GSE68465, GSE33479, GSE31210, GSE30219, GSE10072, GSE27262     |
| TCGA          | TCGA-LUAD, TCGA-LUSC                                           |
| ICGC          | ICGC Lung Cancer cohort                                        |

**Preprocessing pipeline:**
- Cross-dataset merging and harmonisation
- Normalisation and feature scaling
- Handling class imbalance
- Dimensionality management for high-dimensional gene expression profiles

---

##  Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/SyeddNaseer/LUNGXAI.git
cd LUNGXAI
```

### 2. Set Up the Environment

```bash
python -m venv venv
source venv/bin/activate       # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Run the Notebook

Open and run the main notebook:

```bash
jupyter notebook LUNGXAI_.ipynb
```

### 4. Predict on New Data

Pass any gene expression data in CSV format through the trained model to obtain:
- Multi-class classification predictions
- Softmax probability scores
- LIME-based gene-level explanations

---

## 📈 Results Summary

| Metric                  | Score       |
|-------------------------|-------------|
| Accuracy                | **98.8%**   |
| AUC-ROC                 | High (multi-class) |
| Baseline Comparison     | Outperforms SVM, LR, NB, KNN |

Full results and performance metrics are available in the associated manuscript.

---

##  Explainability: Key Contributing Genes

LIME explanations provide gene-level interpretability for each prediction:

| Influence    | Key Genes                                      |
|--------------|------------------------------------------------|
|  Positive  | APP, TAF13, DNMT3B, NFYC, HERC6               |
|  Negative  | CDH6, FBXO46, MAVS, CXCL11, RPL11             |

These gene contributions support **biomarker discovery**, **pathway analysis**, and **network analysis** for clinical and research applications in cancer genomics.

---

## 🧪 Applications

- Lung cancer subtype classification from gene expression profiles
- AI-guided biomarker discovery
- Pathway and gene network analysis
- Drug target prioritisation
- Complement to wet-lab validation workflows

---

## 📂 Repository Structure

```
LUNGXAI/
├── LUNGXAI_.ipynb          # Main notebook: model training, evaluation, and XAI
├── Sample_Data.csv         # Sample gene expression input data
├── README.md               # Project documentation
└── LICENSE.md              # License file
```

---

## ⚠️ Limitations

- Real-time dataset validation is necessary before clinical deployment to ensure reliable outcomes.
- The model is trained on publicly available datasets; performance on institution-specific cohorts may vary.
- High-dimensionality of gene expression data requires significant computational resources.

---

##  License

This project is licensed under the terms described in [LICENSE.md](LICENSE.md).

---

##  Contributions

Contributions, bug reports, and feature suggestions are welcome. Please open an issue or submit a pull request.

---

## 📧 Contact

For questions or collaboration inquiries, please contact:

**Author**: Dr Syed Naseer Ahmad Shah1,2 |  Dr Shaban Ahmad1,3,  | Prof Rafat Parveen1

**Email**: *syed.naseer@galgotiasuniversity.edu.in, Shaban@plen.ku.dk, rparveen@jmi.ac.in*

**Institutions**: *\
1 Department of Computer Science, Jamia Millia Islamia, New Delhi-110025, India.
2. Department of Information Technology at the School of Business, Galgotias University, Greater Noida, India.  
2 MEB Section, Department of Plant and Environmental Sciences, Faculty of Sciences, University of Copenhagen, Frederiksberg C- 1871, Denmark.*


---

## 📖 Citation

If you use LUNGXAI in your research, please cite the associated manuscript (details to be added upon publication).

---
