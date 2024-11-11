# ML-model-comparison
Machine Learning Model Comparison &amp; Hypothesis Testing

## Install
This project requires Python and the following Python libraries installed:

    numPy
    pandas
    matplotlib
    scikit-learn
    seaborn
    mlxtend

We also need to have software installed to run and execute a Jupyter Notebook.

## Data
The dataset consists of 3424 data points with 69 features each collected from Kaggle.

### Features

- Patient ID: Unique ID of each patient
- Age: Age of the patient during their therapy
- Race: Race of the patient from the patient table
- Region: Region of the patient from the patient table
- Ethnicity: Ethnicity of the patient from the patient table
- Gender: Gender of the patient from the patient table
- IDN Indicator: Flag indicating patients mapped to IDN

#### Provider Attributes
- NTM - Physician Specialty: Specialty of the HCP that prescribed the NTM Rx

#### Clinical Factors
- NTM - T-Score: T Score of the patient at the time of the NTM Rx (within 2 years prior from rxdate)
- Change in T Score: Change in Tscore before starting with any therapy and after receiving therapy (Worsened, Remained Same, Improved, Unknown)
- NTM - Risk Segment: Risk Segment of the patient at the time of the NTM Rx (within 2 years days prior from rxdate)
- Change in Risk Segment: Change in Risk Segment before starting with any therapy and after receiving therapy (Worsened, Remained Same, Improved, Unknown)
- NTM - Multiple Risk Factors: Flag indicating if patient falls under multiple risk category (having more than 1 risk) at the time of the NTM Rx (within 365 days prior from rxdate)
- NTM - Dexa Scan Frequency: Number of DEXA scans taken prior to the first NTM Rx date (within 365 days prior from rxdate)
- NTM - Dexa Scan Recency: Flag indicating the presence of Dexa Scan before the NTM Rx (within 2 years prior from rxdate or between their first Rx and Switched Rx; whichever is smaller and applicable)
- Dexa During Therapy: Flag indicating if the patient had a Dexa Scan during their first continuous therapy
- NTM - Fragility Fracture Recency: Flag indicating if the patient had a recent fragility fracture (within 365 days prior from rxdate)
- Fragility Fracture During Therapy: Flag indicating if the patient had fragility fracture during their first continuous therapy
- NTM - Glucocorticoid Recency: Flag indicating usage of Glucocorticoids (>=7.5mg strength) in the one year look-back from the first NTM Rx
- Glucocorticoid During Therapy: Flag indicating if the patient had a Glucocorticoid usage during the first continuous therapy

#### Disease/Treatment Factor
- NTM - Injectable Experience: Flag indicating any injectable drug usage in the recent 12 months before the NTM OP Rx
- NTM - Risk Factors: Risk Factors that the patient is falling into. For chronic Risk Factors complete lookback to be applied and for non-chronic Risk Factors, one year lookback from the date of first OP Rx
- NTM - Comorbidity: Comorbidities are divided into two main categories - Acute and chronic, based on the ICD codes. For chronic disease we are taking complete look back from the first Rx date of NTM therapy and for acute diseases, time period before the NTM OP Rx with one year lookback has been applied
- NTM - Concomitancy: Concomitant drugs recorded prior to starting with a therapy(within 365 days prior from first rxdate)
- Adherence: Adherence for the therapies

Target Variable - `Persistency_Flag` : Flag indicating if a patient was persistent or not

## Analysis
### Model
- Sklearn Logistic regression
- Sklearn Support Vector Machine (SVM)

Using Support Vector Machine Model- Accuracy on Test Dataset is 74.5136186770428 % while using Logistic Regression Model- Accuracy on Test Dataset is 81.22568093385215 %.

We compared both the models with proper pre-processiong of data.
