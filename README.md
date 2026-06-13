Machine Learning Project Review: Fragrance Market Segmentation Using Unsupervised Learning
Project Objective

The primary objective of this project is to discover hidden patterns and natural groupings within a fragrance product dataset using unsupervised machine learning techniques. Since the dataset does not contain predefined labels or target variables, clustering algorithms are employed to identify meaningful segments among products based on their characteristics.

From a business perspective, this analysis can help answer questions such as:

Which fragrances belong to similar market segments?
Are there distinct premium and budget product groups?
Can products be grouped according to customer demand and availability?
Which products behave as outliers in the marketplace?

This type of segmentation is valuable for pricing strategies, inventory management, and targeted marketing campaigns.

Phase 1: Data Understanding and Exploration

The project begins with an extensive Exploratory Data Analysis (EDA).

The notebook first examines:

The dimensions of the dataset,
The structure of the variables,
Data types,
Summary statistics,
Missing values,
Duplicate observations.
Why This Step Is Important

Before building any machine learning model, it is essential to understand the quality and characteristics of the data. Poor-quality data often leads to misleading results regardless of how sophisticated the modelling technique may be.

Through EDA, the analyst gains insight into:

The distribution of variables,
Potential anomalies,
Data completeness,
The suitability of variables for clustering.
Professional Evaluation

This demonstrates a disciplined analytical approach. Rather than immediately applying algorithms, the notebook first validates the integrity of the dataset.

Phase 2: Data Preparation

Once the data structure is understood, preprocessing procedures are applied.

Handling Missing Values

The notebook removes records containing missing values.

Rationale

Incomplete observations can distort distance calculations used by clustering algorithms.

Professional Perspective

Although removing missing values is acceptable in academic settings due to its simplicity, production environments often favour imputation techniques because they preserve valuable information.

Examples include:

Mean or median imputation for numerical variables,
Mode imputation for categorical variables.

Nevertheless, the chosen approach ensures that the remaining dataset is clean and ready for modelling.

Outlier Treatment

Extreme observations are managed by clipping values using lower and upper quantiles.

Purpose

Outliers can disproportionately influence clustering outcomes, particularly in algorithms relying on distance calculations.

Instead of deleting observations entirely, the notebook limits their influence.

Professional Perspective

This strategy is practical because it balances robustness with data retention.

It prevents a few unusual observations from dominating the clustering structure.

Feature Scaling

The notebook standardises numerical variables using StandardScaler.

This transformation adjusts variables so that:

Their mean becomes zero,
Their standard deviation becomes one.
Why It Matters

Clustering algorithms calculate distances between observations.

Without scaling:

Variables measured on larger scales dominate the analysis,
Important variables with smaller ranges become less influential.
Professional Evaluation

Feature scaling is one of the most critical preprocessing steps in clustering workflows, and its inclusion reflects sound machine learning practice.

Phase 3: Product Segmentation Using K-Means Clustering

The first clustering algorithm implemented is K-Means.

Conceptual Overview

K-Means partitions observations into a predefined number of groups by minimising the distance between observations and their assigned cluster centroids.

The algorithm iteratively:

Selects cluster centres,
Assigns observations to the nearest centre,
Updates cluster centres,
Repeats until convergence.
Application in This Project

The algorithm groups fragrances based on attributes such as:

Price,
Units sold,
Product availability,
Brand characteristics,
Product categories,
Geographic information.
Business Interpretation

The resulting clusters may represent:

Cluster A: Premium Segment

Products characterised by:

Higher prices,
Lower sales volumes,
Exclusive availability.
Cluster B: Mass-Market Segment

Products exhibiting:

Moderate pricing,
Broad availability,
Consistent demand.
Cluster C: High-Demand Products

Products with:

Strong sales performance,
Widespread market presence.
Professional Assessment

K-Means provides an intuitive segmentation framework and is widely used in retail analytics. Its application here aligns well with the project's objectives.

Phase 4: Density-Based Segmentation Using DBSCAN

To complement K-Means, the notebook employs DBSCAN.

Conceptual Overview

DBSCAN identifies clusters based on density rather than predefined centroids.

Unlike K-Means, it:

Does not require specifying the number of clusters beforehand,
Detects irregular cluster shapes,
Identifies noise and anomalies.
Why This Is Valuable

Real-world data rarely forms perfectly spherical groups.

Products may naturally cluster in complex patterns.

DBSCAN can reveal structures that K-Means may overlook.

Business Interpretation

Products identified as noise points may indicate:

Niche products,
Rare inventory items,
Potential data quality issues,
Emerging market trends.
Professional Assessment

Including DBSCAN elevates the sophistication of the project by demonstrating awareness that different algorithms capture different underlying structures.

Phase 5: Dimensionality Reduction and Visualisation

High-dimensional datasets are difficult to interpret visually.

The notebook addresses this challenge using PCA and t-SNE.

Principal Component Analysis (PCA)

PCA transforms the original variables into a smaller set of orthogonal components while preserving maximum variance.

Purpose

It simplifies the dataset while retaining most of its informational content.

Benefits
Reduces dimensional complexity,
Facilitates visual exploration,
Improves interpretability.
t-Distributed Stochastic Neighbour Embedding (t-SNE)

t-SNE is a non-linear dimensionality reduction technique.

It focuses on preserving local neighbourhood relationships.

Purpose

To reveal subtle cluster structures that may not be evident through PCA.

Benefits
Produces highly interpretable two-dimensional visualisations,
Highlights local similarities among products.
Professional Assessment

Using both PCA and t-SNE provides complementary perspectives and demonstrates a mature understanding of cluster visualisation techniques.

Phase 6: Cluster Validation

A clustering solution is only valuable if its quality can be objectively assessed.

The notebook evaluates performance using quantitative metrics.

Silhouette Score

This metric measures:

Cohesion within clusters,
Separation between clusters.

Higher values indicate that observations fit well within their assigned groups.

Interpretation

A strong silhouette score suggests meaningful segmentation.

Davies–Bouldin Index

This metric evaluates:

Cluster compactness,
Cluster distinctiveness.

Lower values indicate better clustering quality.

Interpretation

Lower scores imply that clusters are both tight and well separated.

Professional Assessment

Validation transforms clustering from exploratory experimentation into evidence-based analysis. Including these metrics significantly strengthens the credibility of the findings.

Overall Professional Evaluation

From an industry perspective, this notebook demonstrates a well-executed unsupervised learning pipeline.

The workflow follows the standard stages expected in professional analytical practice:

Understanding the data,
Cleaning and preprocessing,
Applying multiple clustering techniques,
Visualising the resulting structures,
Validating the solutions quantitatively.

What distinguishes this project is not merely the implementation of algorithms but the comparative approach taken. By employing both centroid-based and density-based methods, alongside robust validation procedures, the analysis acknowledges that there is rarely a single "correct" clustering solution.

Final Conclusion

This project successfully translates raw fragrance market data into actionable insights through unsupervised machine learning. It demonstrates technical competence in data preprocessing, clustering methodology, visual analytics, and model evaluation. With minor enhancements—such as advanced imputation techniques, more sophisticated categorical encoding, and systematic hyperparameter optimisation—the notebook could readily evolve from an academic assignment into a production-grade analytical framework suitable for real-world business applications.
