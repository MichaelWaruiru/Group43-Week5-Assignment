# Group43-Week5-Assignment


## 📘 Predictive Modeling for Hospital Readmission and Student Dropout

This repository contains two separate predictive modeling projects built in Python using scikit-learn pipelines:

1. **Hospital Readmission Prediction** (using `readmission_data.csv`)
2. **Student Dropout Prediction** (using `student_dataset_v1.csv`)

Both projects use Random Forest classifiers with proper preprocessing pipelines and model evaluation steps.

---

## 📂 Folder Structure (Suggested)

```
.
├── notebooks/
│   ├── readmission_prediction.ipynb
│   └── student_dropout_prediction.ipynb
├── data/
│   ├── readmission_data.csv
│   └── student_dataset_v1.csv
├── models/
│   └── readmission_model.pkl
├── requirements.txt
└── README.md
```

---

## ⚙️ Requirements

Install the exact packages using:

```bash
pip install -r requirements.txt
```

### requirements.txt contents

```
pandas==2.2.2
numpy==1.26.4
scikit-learn==1.4.2
matplotlib==3.8.4
seaborn==0.13.2
joblib==1.4.2
```

---

## 📈 1️⃣ Hospital Readmission Prediction

### 🔹 Dataset Required

* `readmission_data.csv`
* Must contain a `readmitted` column with values 'Yes' or 'No'.

### 🔹 Processing Steps

* Maps target: 'Yes' → 1, 'No' → 0.
* Splits features into numerical and categorical.
* Moves `hospital_stay`, `patient_visits`, `num_diagnosis` to categorical.
* Preprocessing pipeline:

  * Numerical: StandardScaler
  * Categorical: OneHotEncoder (ignore unknowns)

### 🔹 Modeling

* RandomForestClassifier with 100 estimators, max\_depth=10.
* 5-fold stratified cross-validation.
* Final training on train split.

### 🔹 Evaluation

* Confusion matrix
* Classification report
* Precision and recall

### 🔹 Deployment

* Saves trained pipeline to `readmission_model.pkl` using joblib.

### ✅ How to Run

Open the notebook:

```
notebooks/readmission_prediction.ipynb
```

and run cells top to bottom.

Ensure `readmission_data.csv` is in the correct path.

### 🔹 Expected Outputs

* Cross-validated accuracy score.
* Final test confusion matrix.
* Precision, recall.
* Saved model at `models/readmission_model.pkl`.

---

## 📈 2️⃣ Student Dropout Prediction

### 🔹 Dataset Required

* `student_dataset_v1.csv`

### 🔹 Preprocessing Steps

* Drops `Student_Names` column.
* Encodes target `dropout`:

  * Assumes `Comment` == 'Failed' → 1 (dropout)
  * Else → 0
* Drops irrelevant features:

  * `Comment`, `Student_Names`, `Phone_No.`, `Course_Recommendation`, `CourseCode`, `ListofCourses`
* Defines numerical and categorical features:

  * Numerical: `Study_Hours`, `Math`, `Physics`, `Chemistry`, `RatingOfCourses`
  * Categorical: `Gender`, `Part_Time_Job`, `Grade`

### 🔹 Preprocessing Pipeline

* Numerical: StandardScaler
* Categorical: OneHotEncoder (ignore unknowns)

### 🔹 Modeling

* RandomForestClassifier with 100 estimators, max\_depth=10.
* Train/validation/test split:

  * 70% train
  * 15% validation
  * 15% test

### 🔹 Evaluation

* Confusion matrix
* Classification report
* Precision and recall

### 🔹 Feature Importance (Optional)

* Plots top 10 features using seaborn.

### ✅ How to Run

Open the notebook:

```
notebooks/student_dropout_prediction.ipynb
```

and run all cells.

Ensure `student_dataset_v1.csv` is in the correct path.

### 🔹 Expected Outputs

* Confusion matrix on test set.
* Classification report.
* Precision and recall scores.
* Feature importance bar plot (optional).

---

## 💾 Setup Instructions

1️⃣ Clone this repo:

```bash
git clonehttps://github.com/MichaelWaruiru/Group43-Week5-Assignment.git
cd Group43-Week5-Assignment
```

2️⃣ Install dependencies:

```bash
pip install -r requirements.txt
```

3️⃣ Launch Jupyter or VS Code and run notebooks:

```bash
jupyter notebook
```

or

```bash
code .
```

5️⃣ Execute cells top to bottom.

---

## 🗃️ Notes

* Handle missing values before running (check with `data.isnull().sum()`)
* Adjust Random Forest hyperparameters as needed for tuning.
* The saved model (for readmission) can be loaded with joblib.load for deployment in web apps or APIs.

---

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

## Support

If you have any questions or need help, please open an issue or contact [maintainer's contact info].

## License

This project is licensed under the [LICENSE NAME]. See the [LICENSE](LICENSE) file for details.

---