# 03-Titanic-Survival

This is my third portfolio project, tackling the classic Kaggle "Titanic" dataset. The primary goal was not model complexity, but mastering **data cleaning** and **feature engineering** on a messy, real-world dataset.

## 🎯 Project Goal

To build a machine learning model that predicts whether a passenger survived the Titanic shipwreck. The project involved a 3-step process:
1.  **Data Auditing:** Investigating missing and non-numeric data.
2.  **Data Cleaning & Feature Engineering:** Imputing, dropping, and transforming features to make them usable.
3.  **Model Building:** Training a `RandomForestClassifier` on the clean data.

## 🧹 Data Cleaning & Feature Engineering

This was the core of the project. The raw `train.csv` could not be used directly.

My full analysis is in `titanic_analysis.ipynb`, but here are the key steps:

* **`Age`:** Had 177 missing values. I imputed these using the dataset's **median** age.
* **`Cabin`:** Was ~80% missing. I **dropped** this feature entirely.
* **`Embarked`:** Had 2 missing values. I imputed these with the **mode** (most common port, 'S').
* **`Sex`:** Converted from text ('male'/'female') to a single numeric column (`Sex_male` 0 or 1).
* **`Embarked`:** Converted from text ('S', 'C', 'Q') to two numeric dummy columns.
* **Dropped Features:** I also dropped `Name`, `Ticket`, and `PassengerId` as they were not useful for this baseline model.

## 🤖 Model Performance

I used a `RandomForestClassifier` (100 trees) and split the data into 80% training and 20% testing.

* **Final Model Accuracy:** **~82%** on the unseen test data.

The confusion matrix shows the model is strong at predicting passengers who did not survive (True Negatives) and reasonably good at predicting those who did (True Positives).

## 🏃 How to Run This Project

1.  Clone this repository: `git clone https://github.com/YourUsername/titanic-survival.git`
2.  Navigate to the folder: `cd titanic-survival`
3.  **Important:** Download the `train.csv` and `test.csv` from the [Kaggle Titanic Data Page](https://www.kaggle.com/c/titanic/data) and place them in the `data/` folder.
4.  Install the required libraries (if you don't have Anaconda):
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn jupyter
    ```
5.  Open the notebook:
    ```bash
    jupyter notebook titanic_analysis.ipynb
    ```