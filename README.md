### Exploring diabetes data

**Brad Long**

#### Executive summary
Diabetes is a chronic disease which affects how your body turns food into energy.  Diabetes is the eighth leading cause of death in the US, and the number one cause of kidney failure, lower limb amptutations, and adult blindness (https://www.cdc.gov/diabetes/basics).  The symptoms of diabetes can range from dryness of mouth to fatigue to blurred vision.  Many of these symptoms could be attributed to other underlying medical conditions so developing a method of identifying candidates for further testing would help with earlier detection. This project attempts to build a model to identify whether someone has diabetes using very simple diagnostic measures, most of which would be collected during any routine visit to the doctor (or which could be accomplished at home).

#### Rationale
My son was diagnosed with Type 1 diabetes a little more than eight years ago.  Many times, diabetics only find out they have diabetes through an acute issue known as diabetic ketoacidosis which usually leads to unconciousness and a trip to the emergency room if not identified early enough.  Routine doctors visits and monitoring common medical measurements can prevent a condition from reaching this severity before diagnosis.  Since the symptoms may be attributed to other underlying medical conditions, it's possible that a diabetes diagnosis may be missed or not considered at all.  Although there is no cure for diabetes, lifestyle changes and proper management can minimize the long-term risks the disease presents.  Early identification is crucial to minimizing these potential impacts. 

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

I decided to look for another diabetes data set to leverage and found that kaggle hosts a great dataset (https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database/) which is perfect for the model I am attempting to build.  Pima Indians have been know to have a higher incidence of diabetes than surrounding populations.  Based on isolation from surrounding regions and a willingness to participate, the Pima community provides an ideal population to study.  Although hosted on kaggle, the dataset originates from National Institute of Diabetes and Digestive and Kidney Diseases.  It has been widely used and is a good choice since it's provenance is known.

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
I found that the best model was SVM with parameters: C=10; gamma=scale; kernel=rbf.  There are a couple of different possibilities to consider when deciding looking at the models effectiveness.  The four cases are True-Positive, True-Negative, False-Positive, False- Negative.  The SVM model was able to identify 90% of True-Negatives and 74% or True-Positives.  With those numbers, a low percentage of those with diabetes would be told they didn't have it (the False-negatives, 10%), and a high number of those with diabetes would be identified as having it (True-Positive, 74%).  Overall, this particular model delivered 84% accuracy which when combined with the low False-Negative and high True-Positive make it a good solution. 

#### Next steps
This particular dataset was utilized to leverage a small group of biometric measures to determine whether a patient has diabetes.  A potential next step would be to look at a test dataset from a separate population to evaluate the model.  Does the model work across different populations or is there something particular to the Pima Indian population that isn't captured within this dataset. 

#### Outline of project

- [https://github.com/013786/Capstone/blob/main/long_capstone.ipynb] (Link to Capstone Notebook)
- [https://github.com/013786/Capstone/blob/main/README.md] (Link to README)
- [https://github.com/013786/Capstone/tree/main/data] (Link Data Folder)


##### Contact and Further Information
Brad Long
bradlong@cisco.com
