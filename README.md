### Exploring diabetes data

**Brad Long**

#### Executive summary
Diabetes is a chronic disease which affects how your body turns food into energy.  Diabetes is the eighth leading cause of death in the US, and the number one cause of kidney failure, lower limb amptutations, and adult blindness (https://www.cdc.gov/diabetes/basics).  This project attempts to build a model to identify whether someone has diabetes using very simple diagnostic measures.

#### Rationale
My son was diagnosed with Type 1 diabetes a little more than eight years ago.  Many times, diabetics only find out they have diabetes through an acute issue known as diabetic ketoacidosis which usually leads to unconciousness and a trip to the emergency room if not identified early enough.  Routine doctors visits and monitoring common medical measurements can prevent a condition from reaching this severity before diagnosis.

#### Research Question
I am trying to be able to predict whether or not someone has diabetes based on a group of independent variables:
    Pregnancies: Number of times a woman has been pregnant
    Glucose: Plasma Glucose concentration of 2 hours in an oral glucose tolerance test
    BloodPressure: Diastollic Blood Pressure (mm hg)
    SkinThickness: Triceps skin fold thickness(mm)
    Insulin: 2 hour serum insulin(mu U/ml)
    BMI: Body Mass Index ((weight in kg/height in m)^2)
    Age: Age(years)
    DiabetesPedigreeFunction: Likelihood of diabetes based on family history

#### Data Sources
Initially I was planning to explore data from my son's medical devices.  I had access to things like blood glucose level, insulin (both basal - background insulin to keep blood glucaose level steady - and bolus - used in response to meals), general bio info (height, weight, etc), and more.  Currently he uses a closed loop system consisting of blood glucose measurement and automated insulin delivery to regulate his diabetes.  As I thought about it, I realized it would be challenging to establish a control or baseline set of data since everything associated with his readings is intertwined.

I decided to look for another diabetes data set to leverage and found that kaggle has a great dataset (https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database/) that has been widely used and would be a good choice since it's provenance is known.

#### Methodology
The following steps were followed during this project:
  - Load libraries and import data
  - Assess the data and perform preprocessing (including initial visualizations)
  - Address outliers (and drop columns which do not have strong correlations)
  - Split into training and test data sets
  - Perform classification using a variety of classifiers to identify the best model
      -- Each model utiziled gridsearch to identify the best parameters for that particular model
  - Assess the most accurate model

#### Results
I found that the best model was SVM with parameters: C=10; gamma=scale; kernel=rbf.

#### Next steps
This particular dataset was utilized to leverage a small group of biometric measures to determine whether a patient has diabetes.  A potential next step would be to look at a test dataset from a separate population to evaluate the model.  Does the model work across different populations or is there something particular to the Pima Indian population that isn't captured within this dataset. 

#### Outline of project

- https://github.com/013786/Capstone/blob/main/long_capstone.ipynb
- https://github.com/013786/Capstone/blob/main/data/

##### Contact and Further Information
Brad Long
bradlong@cisco.com
