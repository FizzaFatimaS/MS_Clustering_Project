# Customer Segmentation Using Machine Learning for E-Commerce Marketing

## 📌 Project Overview

This repository contains the implementation of multiple **unsupervised machine learning techniques** for customer segmentation in an e-commerce context. The objective of the project is to identify meaningful customer segments based on purchasing behaviour and transactional data, which can later be used to support **personalised marketing campaigns** and improve conversion rates.

The project systematically evaluates both traditional clustering algorithms and deep learning–based approaches using quantitative clustering metrics.

> **Note:** The dataset used in this project belongs to a commercial organisation and therefore cannot be shared publicly. As a result, some preprocessing and exploratory steps are described conceptually rather than implemented in executable code.

---

## 📂 Repository Structure

```
├── Customer_Segmentation_Via_Clustering.ipynb
├── README.md
```

* **Customer_Segmentation_Via_Clustering.ipynb**
  Main notebook containing all experiments, clustering methods, evaluations, and visualisations.

---

## 🔐 Data Availability & Privacy

* The original dataset is **company-owned and confidential**.
* Dataset-specific preprocessing and feature engineering steps are **not included in code form** to avoid exposing sensitive business information.
* Instead, these steps are **clearly described in text** within the notebook.
* All clustering, evaluation, and visualisation code is provided in full and can be reused with a suitable dataset.

---

## 🧹 Data Preprocessing & EDA

The following steps are **described conceptually** in the notebook:

* Data cleaning and handling of missing values
* Feature selection and aggregation at the customer level
* Creation of behavioural and transactional features
* Exploratory Data Analysis (EDA) to understand distributions and outliers

To support reproducibility without exposing raw features:

* Code for **correlation heatmaps**
* Code for **correlation value inspection**

are included and can be applied to any similar dataset.

---

## 📈 Principal Component Analysis (PCA)

In the notebook PCA shows:

  * Explained variance analysis
  * Selection of optimal components

## 🧠 Methods Implemented

The notebook contains implementations of the following techniques:

### 1. Traditional Machine Learning Clustering Algorithms

* **K-Means**

  * Elbow Method
  * Grid Search over:

    * Number of clusters
    * Initialisation methods
    * `n_init` values
* **Gaussian Mixture Models (GMM)**

  * Grid Search over:

    * Number of components
    * Covariance types (full, tied, diag, spherical)
* **BIRCH**

  * Grid Search over:

    * Number of clusters
    * Threshold values

### 2. Deep Learning Based Clustering Algorithms

* **Autoencoder + K-Means**

  * Grid Search over:

    * Latent dimensions
    * Number of clusters
    * Learning rates
* **Deep Embedded Clustering (DEC)**

  * Autoencoder-based representation learning
  * Soft assignment refinement using Student’s *t*-distribution
  * Grid Search over:

    * Latent dimensions
    * Number of clusters
    * Learning rates

---

## 📊 Evaluation Metrics

All clustering methods are evaluated using:

* **Silhouette Score**
  Measures cluster cohesion and separation (higher is better)

* **Davies–Bouldin Index (DBI)**
  Measures average cluster similarity (lower is better)

These metrics are computed for every parameter combination during grid search.

---

## 📈 Visualisation

The notebook includes code for:

* Correlation heatmaps
* PCA variance plots
* Radar charts for:

  * Cluster-wise feature profiling
  * Interpretation of customer behaviour
* Visualisation of **best-performing clustering models**

Cluster labels are mapped back to the **original customer records** (including `UserIdentifier`) to support interpretability and downstream business analysis.

---

## 🏆 Model Selection

Although several models achieved strong quantitative performance, final model selection considered:

* Clustering quality (Silhouette & DB Index)
* Cluster balance
* Business interpretability

While **Deep Embedded Clustering (DEC)** achieved the highest scores, its highly imbalanced clusters were not considered business-meaningful.
The final selected model was **Autoencoder + K-Means**, which provided a strong balance between performance and interpretability.

---

## ⚙️ Technologies Used

* **Python**
* **Pandas, NumPy**
* **Scikit-learn**
* **TensorFlow**
* **Matplotlib, Seaborn**

---

## 🚀 How to Use This Repository

1. Clone the repository
2. Open the notebook in Jupyter or Google Colab
3. Replace the dataset loading step with your own dataset
4. Adjust preprocessing steps as needed
5. Run clustering and evaluation sections independently

---

## 📄 License

This repository is intended for **academic and educational use only**.
Commercial reuse of the methodology should ensure compliance with data privacy and business confidentiality requirements.
