## Overview
- This repository contains the practical submission for Group 43’s Week 5 assignment, focusing on the AI development Workflow such problem definition, Data collection and preprocessing, model development (model selection and training), Model evaluation and deployment, Ethical consideration and reflection. 
- Real-world datasets was employed. 
- The implementation leverages popular Python libraries: Scikit-learn etc. 
- The goal is to develop solutions, analyze results, and reflect on the ethical implications of AI models.

## Table of Content
- Part 1: Hypothetical AI Problem: Predicting student dropout rates in higher education institutions
- Part 2: Case Study: Predicting 30-Day Hospital Readmission Risk Using AI
- Part 3: Part 3: Critical Thinking- Ethics, Bias and & Trade-off
- Part 4: Reflection & Workflow Diagram

- Getting Started
- Requirements
- How to Run
- Contributing
- License

## Part 1: Short Answer Questions
### 1. Problem Definition
- Hypothetical AI Problem: Predicting student dropout rates in higher education.

### Objectives:
- Identify students at risk of dropping out early.
- Enable timely support through intervention.
- Reduce dropout rates and institutional costs.

### Stakeholders:
- University administrators
- Academic advisors and student services

### KPI: Dropout prediction accuracy (e.g., % of correctly identified at-risk students)

### 2. Data Collection & Preprocessing
- Data Sources: Kaggle – Student Data CSV
- SIS: Academic records, attendance, course enrollment
- LMS: Assignment submissions, login frequency

### Potential Bias:
- Socioeconomic bias affecting underrepresented groups

### Preprocessing Steps:
- Impute or drop missing values
- Normalize numerical features (grades, attendance)
- Encode categorical features (gender, major, program type)

### 3. Model Development
- Model: Random Forest Classifier
- Handles non-linear patterns
- Interpretable via feature importance
- Robust to outliers

### Data Split:
- Train: 70%
- Validation: 15%
- Test: 15% (using stratified sampling)

### Hyperparameters:
- n_estimators
- max_depth

### 4. Evaluation & Deployment
- Metrics:
- Precision: Minimize false positives
- Recall: Maximize detection of at-risk students
- Concept Drift:
- Definition: Change in input distribution over time
- Monitoring: Rolling evaluations, use of DDM/ADWIN, retraining
- Technical Challenge: Scaling model for real-time, cross-campus inference


## Part 2: Case Study – 30-Day Hospital Readmission
### 1. Problem Scope
### Objective: Predict risk of 30-day readmission to reduce care gaps and costs

### Stakeholders:
- Clinicians, administrators, care coordinators, patients, compliance teams

### 2. Data Strategy
- Data Sources:
- EHRs: Diagnoses, procedures, labs, medications
- Demographics: Age, gender, ethnicity
- Social factors: Housing, support, insurance status

### Ethical Concerns:
- HIPAA-compliant anonymization
- Bias audits to protect vulnerable populations

### Preprocessing Steps:
- Handle missing values & remove duplicates
- Feature engineer binary target and aggregate counts
- Encode categorical data
- Normalize numerical features
- Stratified train/test split

### 3. Model Development
- Model: Random Forest Classifier
- Metrics (hypothetical):
- = 0.727
- Recall = 0.800
### 4. Deployment
- Steps:
- Serve via RESTful API
- Integrate with EHR UI
- Trigger clinician alerts
- Monitor & retrain regularly

### Compliance:
- Encryption, audit logs
- Consent tracking
- Explainable outputs

### 5. Optimization
- Overfitting Prevention:
- Use k-fold cross-validation
- Employ early stopping and hyperparameter tuning

## Part 3: Critical Thinking
- Ethics & Bias
- Impact: Historical bias may cause under-detection in marginalized groups.
- Mitigation:
- Fair representation via reweighting
- Fairness-constrained algorithms
- Subgroup performance audits
- References:


Trade-offs
Accuracy vs. Interpretability:


## Part 4: Reflection
### Most Challenging Stage: Preprocessing—handling missing data, engineering features, and mitigating bias.

### Improvement Opportunities:
- Use IBM AI Fairness 360 or Aequitas
- Build real-time ETL pipelines
- Collaborate across ethics, clinical, and data science teams
- References

### Diagram
AI Development Lifecycle flowchart: Problem Definition → Data Collection → Preprocessing → Modeling → Evaluation → Deployment → Monitoring → Continuous Improvement 

## Getting Started
- Clone this repository:

- git clone https://github.com/MichaelWaruiru/Group43-Week5-Assignment.git

## Requirements 
Python 3.7+
Jupyter Notebook
pandas, scikit-learn
Google Colab
Install requirements (recommended in a virtual environment):

pip install -r requirements.txt
Note: If requirements.txt is missing, install packages individually as shown above

### How to Run
- Launch Jupyter Notebook: jupyter notebook
- Open the desired noteboo and run the cells.

## Authors & Acknowledgments
- Group 43, AI for Software Engineering,FebCohort 2025.

## Contributing
- Contributions are welcome! Please fork the repository and open a pull request with your proposed changes.

## License
- This repository is for educational purposes. See the LICENSE file for details (if available).

## More Information
- For details on each notebook, consult the inline documentation and comments within each .ipynb file.
