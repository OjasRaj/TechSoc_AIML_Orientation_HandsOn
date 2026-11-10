# TechSoc_AIML_Orientation_HandsOn

Tumor Diagnostics Classification

This project demonstrates a complete, hands-on machine learning pipeline for classifying tumor diagnostics using the classic **Breast Cancer Wisconsin Dataset** provided by `scikit-learn`.

## 📌 Project Overview
The goal is to classify whether a tumor is **malignant (1)** or **benign (0)** using medical measurements. For simplicity and clarity of visualization, we focus on a single input feature: **the mean radius of the tumor cells**.

---

## 🛠️ The Machine Learning Pipeline

### 1. Data Loading & Exploration
* **Source:** Breast Cancer Wisconsin Dataset (`sklearn.datasets.load_breast_cancer`).
* **Features:** Mean radius of the tumor.
* **Target:** Binary classification label where `1` represents **Malignant** and `0` represents **Benign**.
* **Visualizations:** The dataset is explored using scatter plots and Kernel Density Estimation (KDE) density plots to observe the overlap and distributions between classes.

### 2. Train-Test Split
To evaluate how well our model generalizes to unseen data, we split our original dataset of 200 samples:
* **Training Set (80% / 160 samples):** Used as the textbook for the model to study.
* **Testing Set (20% / 40 samples):** Used as the final exam to evaluate the model's performance.

### 3. Data Cleaning & Outlier Removal
Biological data often contains anomalous inputs. We filter the training dataset by removing extreme statistical outliers (data points that fall outside of **2 standard deviations** from the mean radius of the training dataset). This process removed 4 outlier records, resulting in 156 clean training samples.

### 4. Model Development (Decision Tree)
* **Algorithm:** Decision Tree Classifier (`DecisionTreeClassifier`).
* **Hyperparameter:** `max_depth=3` to limit tree complexity, prevent overfitting, and ensure the rules are easy to interpret.

### 5. Performance Evaluation
After making predictions on the unseen test set, we assess model performance using four key metrics:
* **Accuracy (77.50%):** The percentage of overall diagnoses correctly predicted.
* **Precision (81.82%):** Out of all tumors we predicted as malignant, how many actually were.
* **Recall (78.26%):** Out of all actual malignant tumors, how many did the model capture.
* **F1-Score (80.00%):** The balanced harmonic mean of Precision and Recall.

### 6. Decision Boundary Visualization
A visualization plotting the continuous decision boundary line of our Decision Tree against the scatter plot of the actual test dataset. This showcases the exact classification cut-offs chosen by the tree.

---

## 💻 Tech Stack & Dependencies
* **Python 3**
* **NumPy** & **Pandas** (Data Manipulation)
* **Matplotlib** & **Seaborn** (Data Visualization)
* **Scikit-Learn** (Machine Learning Model & Metrics)
```
