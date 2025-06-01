# Case-Study-Customer-Segmentation-for-a-Telecom-Operator

#Telco Customer Segmentation: Project Summary


---


1. **Data Loading & Exploration**

* Loaded the telco.csv dataset to examine the structure, data types, and detect issues like missing values.

* Identified that the TotalCharges column contained non-numeric entries and missing values.

2. **Data Preprocessing**

* Converted TotalCharges to numeric with errors='coerce' to handle non-numeric entries.

* Imputed missing TotalCharges values using median.

 *Checked for and handled duplicate records.*

* Identified outliers in continuous variables (tenure, MonthlyCharges, TotalCharges) using boxplots.

* Outlier detection was skipped for binary categorical columns like SeniorCitizen where it’s not meaningful.

3. **Feature Engineering**

* Selected relevant features for clustering based on business logic.

* Applied One-Hot Encoding to categorical variables.

* Scaled numerical features using StandardScaler to ensure uniform contribution to distance metrics.

4. **Determining Optimal Number of Clusters (k)**
* Used the Elbow Method to analyze KMeans inertia.

* Used Silhouette Score to validate cluster separation and compactness.

* Selected optimal k (e.g., k=3) based on both metrics.

5. **K-Means Clustering**
* Applied KMeans clustering with the chosen k and n_init=10 to ensure stable results.

* Checked cluster stability by rerunning KMeans with different random seeds and computing silhouette scores across runs.

* Assigned resulting cluster labels to the original DataFrame.

6. **Cluster Profiling**

Analyzed cluster characteristics by calculating:

* Mean and median for continuous features (tenure, MonthlyCharges, TotalCharges).

* Frequency distributions for categorical variables (InternetService, Contract, PaymentMethod).

* Created a summarized cluster profile for easy interpretation.

7. **Business Labeling**

* Assigned descriptive labels to clusters (e.g., "Budget-conscious", "Mid-range loyalists", "High-value users"), aiding business teams in interpreting the segments.

* Mapped these labels back to the customer data.

8. **Cluster Visualization**

* Applied PCA (Principal Component Analysis) to reduce the feature space to 2D for visualization.

* Created a scatter plot of the PCA-transformed data colored by cluster label.

* Used boxplots and countplots to compare feature distributions across clusters.



