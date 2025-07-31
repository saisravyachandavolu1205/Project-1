**Project Overview**
This project analyzes historical wildfire data from California to predict the risk level of wildfire incidents (Low, Medium, High) using machine learning models. Through careful data preprocessing, dimensionality reduction with PCA, and training classification models like Random Forest, SVM, and XGBoost, the project aims to support disaster planning and emergency response strategies.

**Dataset**
The dataset (California Fire Incidents.csv) contains real fire incident data including:
Acres Burned
Structures Threatened / Damaged / Destroyed
Resources Deployed (Engines, Dozers, Personnel, etc.)
Injuries, Fatalities
Location and Containment Status
A new label Risk Category was engineered from Acres Burned:
Low Risk: ≤ 35 acres
Medium Risk: 36–100 acres
High Risk: > 100 acres

**Preprocessing & Feature Engineering**
Removed non-predictive metadata fields
Filled missing numeric values (0 for resources, dropped for critical fields like acres)
Encoded categorical fields using One-Hot and Label Encoding
Created RiskCategory label for classification
Applied PCA to retain 95% variance and reduce dimensionality

**Machine Learning Models**
Three classifiers were trained and evaluated:
Random Forest (best without PCA)
Support Vector Machine (SVM) (best with PCA)
XGBoost (best overall with PCA + tuning)
| Model         | Without PCA | With PCA      |
| ------------- | ----------- | ------------- |
| Random Forest | 72.78%      | ↓ lower       |
| SVM           | 71.25%      | **73.39%**    |
| XGBoost       | N/A         | **🏆 75.55%** |

**Visualizations Included**
Wildfire Incidents by Year
Acres Burned Distribution
Acres vs. Personnel Scatter Plot
Correlation Heatmap
Confusion Matrices

**Key Takeaways**
PCA improved performance for SVM & XGBoost
Random Forest was the most robust out-of-the-box model
XGBoost achieved the highest accuracy after tuning
Feature importance showed AcresBurned, FireCause, and County as the top predictors

**Future Improvements**
Add real-time weather and environmental data
Explore deep learning models
Use smarter imputation (e.g., KNN Imputer)
Evaluate models with Precision, Recall, and F1-Score


