# Customer Segmentation and Lookalike Modeling for eCommerce

## Overview

This repository contains code and analysis for customer segmentation and lookalike modeling applied to an eCommerce transactions dataset. The goal of this project is to:

1. **Segment customers** into distinct groups based on their purchasing behavior and profile characteristics using clustering techniques.
2. **Build a lookalike model** to identify customers who are similar to a given customer based on their features.

The insights gained from this analysis can be used to inform targeted marketing campaigns, personalize customer experiences, and improve customer acquisition and retention strategies.

## Repository Structure

```
zeotap-assignment-2025-data-science/
├── data/
│   ├── Customers.csv
│   ├── Products.csv
│   └── Transactions.csv
├── Gurveer_Singh_Virk_Clustering.ipynb
├── Gurveer_Singh_Virk_Clustering.pdf
├── Gurveer_Singh_Virk_EDA.ipynb
├── Gurveer_Singh_Virk_EDA.pdf
├── Gurveer_Singh_Virk_Lookalike.csv
├── Gurveer_Singh_Virk_Lookalike.ipynb
└── README.md
```

*   **`data/`:** Directory containing the raw datasets:
    *   **`Customers.csv`:** Dataset containing customer profile information (e.g., ID, name, region, signup date).
    *   **`Products.csv`:** Dataset containing product information (e.g., ID, name, category, price).
    *   **`Transactions.csv`:** Dataset containing transaction history (e.g., customer ID, product ID, transaction date, quantity, total value).
*   **`Gurveer_Singh_Virk_Clustering.ipynb`:** Jupyter Notebook containing the code and analysis for customer segmentation (Task 3).
*   **`Gurveer_Singh_Virk_Clustering.pdf`:** PDF report summarizing the clustering results.
*   **`Gurveer_Singh_Virk_EDA.ipynb`:** Jupyter Notebook containing the code and analysis for Exploratory Data Analysis (EDA) (Task 1).
*   **`Gurveer_Singh_Virk_EDA.pdf`:** PDF report summarizing the EDA findings and business insights.
*   **`Gurveer_Singh_Virk_Lookalike.csv`:** Output file containing the top 3 lookalike customers for the first 20 customers in the `Customers.csv` dataset.
*   **`Gurveer_Singh_Virk_Lookalike.ipynb`:** Jupyter Notebook containing the code and analysis for the lookalike model (Task 2).
*   **`README.md`:** This file, providing an overview of the repository.

## Tasks

### Task 1: Exploratory Data Analysis (EDA) and Business Insights

This task involves performing a thorough exploratory data analysis (EDA) on the provided datasets to understand the data, identify patterns, and derive actionable business insights. The EDA includes:

*   Data loading, cleaning, and preprocessing.
*   Univariate, bivariate, and multivariate analysis using descriptive statistics and visualizations.
*   Derivation of at least 5 key business insights from the data.

**Deliverables:**

*   **`Gurveer_Singh_Virk_EDA.ipynb`:** A Jupyter Notebook containing the EDA code, visualizations, and comments.
*   **`Gurveer_Singh_Virk_EDA.pdf`:** A PDF report summarizing the findings with business insights.

### Task 2: Lookalike Model

This task involves building a lookalike model that recommends similar customers based on a given customer's profile and transaction history.

**Methodology:**

1. **Feature Engineering:** Created relevant features from the customer and transaction data, including:
    *   One-hot encoding of categorical features (e.g., Region, product categories).
    *   Extraction of date components (e.g., signup year, month).
    *   Calculation of RFM metrics (Recency, Frequency, Monetary Value).
    *   Aggregation of transaction data to the customer level.
2. **Feature Scaling:** Standardized numerical features using `StandardScaler`.
3. **Similarity Calculation:** Computed the cosine similarity between customers based on the engineered features.
4. **Lookalike Recommendation:** Developed a function to find the top N most similar customers (lookalikes) for a given customer based on the cosine similarity scores.

**Deliverables:**

*   **`Gurveer_Singh_Virk_Lookalike.ipynb`:** A Jupyter Notebook explaining the model development process, including feature engineering, similarity calculation, and recommendation logic.
*   **`Gurveer_Singh_Virk_Lookalike.csv`:** A CSV file containing the top 3 lookalike customers (with similarity scores) for the first 20 customers in the `Customers.csv` dataset, in the format `Map<cust_id, List<cust_id, score>>`.

### Task 3: Customer Segmentation

This task involves using clustering techniques to segment customers into distinct groups based on their profile and transaction information.

**Methodology:**

1. **Feature Engineering:** Used the same features engineered in Task 2 (with additional features like Signup Year and Month).
2. **Handle Missing Values:** Filled missing values appropriately (e.g., 0 for monetary-related features, a large value for recency).
3. **Feature Scaling:** Standardized numerical features using `StandardScaler`.
4. **Clustering:** Applied the K-Means clustering algorithm.
5. **Determine Optimal k:** Used the Elbow Method, Davies-Bouldin Index, Silhouette Score, and Calinski-Harabasz Score to determine the optimal number of clusters (k).
6. **Cluster Evaluation:** Evaluated the clustering results using the Davies-Bouldin Index, Silhouette Score, and Calinski-Harabasz Score.
7. **Cluster Visualization:** Generated scatter plots and other visualizations to visualize the clusters and their characteristics.
8. **Cluster Profiling:** Analyzed the mean values of features within each cluster to understand their key characteristics.

**Deliverables:**

*   **`Gurveer_Singh_Virk_Clustering.ipynb`:** A Jupyter Notebook containing the code for data preprocessing, feature engineering, clustering, evaluation, and visualization.
*   **`Gurveer_Singh_Virk_Clustering.pdf`:** A PDF report summarizing the clustering results, including:
    *   The number of clusters formed (k).
    *   Clustering metrics (DB Index, Silhouette Score, Calinski-Harabasz Score).
    *   Descriptions of each cluster's characteristics.
    *   Visualizations of the clusters.