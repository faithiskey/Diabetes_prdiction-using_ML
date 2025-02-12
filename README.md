📌 Project Overview

This project predicts the likelihood of diabetes in patients based on various health indicators using a Random Forest Classifier. The dataset includes features like age, BMI, blood glucose levels, hypertension, and smoking history.

1. Importing Required Libraries
   .pandas (pd): Handles tables and spreadsheets.
   .numpy (np): Helps with number crunching.
   .matplotlib.pyplot (plt): Creates graphs.
  .seaborn (sns): Makes better-looking graphs.
  .sklearn (scikit-learn): Provides tools for training and testing machine learning models.

2. Loading the Dataset
Reads a CSV file that contains patient health data.

3. Checking Data Overview
df.info(): Shows column names, data types, and missing values.
df.shape: Tells how many rows and columns are in the dataset.
df.isnull().sum(): Checks for missing values.

4. Filtering Data
filtered_df = df[(df["age"] >= 50) & (df["hypertension"] == 1) & (df["diabetes"] == 1)]
print(filtered_df) -Finds patients above 50 years old with hypertension and diabetes.

below_50_filtered_df = df[(df["age"] <= 49) & (df["hypertension"] == 1) & (df["diabetes"] == 1)]
print(below_50_filtered_df) -Finds similar patients but below 50 years old.

5. Analyzing Categorical Data
   categorical_cols = ["gender", "hypertension", "heart_disease", "smoking_history", "diabetes"]

for col in categorical_cols:
    print(f"Distribution of {col}:")
    print(df[col].value_counts())
    print() -Checks how many patients belong to each category (e.g., male/female, smokers, etc.).

    female_df = df[df["gender"] == "Female"]
print("Female Smoking History:")
print(female_df["smoking_history"].value_counts()) -Filters female patients and checks their smoking history.

6. Visualizing Categorical Data
  - Creates bar charts for categorical data.

7. Analyzing Numeric Data
- Creates histograms to understand numerical data distribution.
  
Boxplot
Compares BMI between males and females using a box plot.

 8. Correlation Analysis
    The numbers in the table range from -1 to 1. Here's what they mean:

1: Perfect positive correlation (when one variable increases, the other increases too)

-1: Perfect negative correlation (when one variable increases, the other decreases)

0: No correlation (the variables don't seem to be related)

Age vs. BMI: The correlation is 0.337396, which means there's a moderate positive correlation. As people get older, their BMI tends to increase.

Age vs. HbA1c_level: The correlation is 0.101354, which means there's a weak positive correlation. As people get older, their HbA1c levels might increase slightly.

Age vs. Blood Glucose Level: The correlation is 0.110672, which means there's a weak positive correlation. As people get older, their blood glucose levels might increase slightly.

The table shows how different health metrics are related to each other. For example, as people get older, their BMI tends to increase. There's also a weak connection between age and blood glucose levels. This information can help us understand how different health factors are connected

9. Preparing Data for Machine Learning
    -Defines diabetes as the target (what we want to predict).
    -Splits the data into 80% training and 20% testing.

   Handling Categorical Data
   -Converts male/female into numbers (e.g., Male → 0, Female → 1). so that it can be used for prediction, it must be in numerical value.
   -Converts all categorical columns into numbers.

   10. Training the Machine Learning Model
       - Uses a Random Forest Classifier, a strong machine learning model
      
    11. Making Predictions
        -Predicts whether test patients have diabetes.

  12. Evaluating the Model
-  The Measures accuracy (percentage of correct predictions) was 97%.
