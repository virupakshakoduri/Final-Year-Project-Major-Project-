#  Student Alcohol Consumption Detection (ML Classification)

This project, developed in a Jupyter Notebook (`student-alcohol-consump-project.ipynb`), is a machine learning initiative aimed at predicting the likelihood of **high alcohol consumption** among high school students. It uses a range of social, demographic, and academic features to classify students into a high-risk group, providing a valuable tool for early intervention and support programs. The task is structured as a **binary classification** problem.

---

##  Methodology and Skills Demonstrated

The project involved meticulous data science techniques from initial cleaning through final model selection.

### 1. Data Preparation and Feature Engineering
The initial step involved merging two separate datasets, `student-mat.csv` (Math course) and `student-por.csv` (Portuguese course). The data was combined using a shared set of 30 non-grade related features as keys, and **duplicate student entries were removed** to ensure data integrity, resulting in a clean dataset of **370 unique student records**. A key feature engineering step was the creation of the target variable: the workday consumption (`Dalc`) and weekend consumption (`Walc`) features were averaged to create a composite weekly consumption score (`Alc`). This score was then converted into the binary target variable, **`high_alc`**, where any average consumption score **greater than 2** was classified as 'high' (1). Finally, all categorical text features were prepared for modeling using **One-Hot Encoding**.

### 2. Models and Algorithms Used
Six distinct machine learning classification algorithms were trained and compared to find the most effective predictor. The models included a mix of simpler tree models and powerful ensemble/boosting techniques:

* **Decision Tree Classifier**
* **Random Forest Classifier**
* **Support Vector Machine (SVC)**
* **Extra Trees Classifier**
* **AdaBoost Classifier** (Boosting Ensemble)
* **Light Gradient Boosting Machine (LightGBM)** (Gradient Boosting Ensemble)

---

##  Performance and Key Findings

The models were evaluated on an unseen test set to assess their generalization capabilities.

### Best Model Performance
The **Light Gradient Boosting Machine (LightGBM)** consistently outperformed all other classifiers, establishing itself as the final production model.

* **Highest Accuracy:** **0.878378** (approximately **87.8%**)
* **Highest Precision:** **0.868421**

### Model Interpretation
The high **Precision** score achieved by LightGBM is particularly significant for this type of problem. A precision of 86.8% means that when the model flags a student as high-risk, it is **correct nearly 87% of the time**. This minimizes **False Positives** (incorrectly flagging a low-risk student), ensuring that limited intervention and counseling resources are directed efficiently toward genuinely at-risk individuals. The remaining models trailed slightly, with Random Forest and Extra Trees achieving the next best accuracy at **0.864865**.

---

##  Conclusion and Future Enhancements

The project successfully delivered a robust predictive model for student alcohol consumption risk using standard machine learning libraries like `scikit-learn` and `lightgbm`. Future work would focus on **hyperparameter tuning** to maximize the F1-score (balancing Precision and Recall) and developing a **production pipeline** to deploy the LightGBM model as a real-time risk assessment tool.
