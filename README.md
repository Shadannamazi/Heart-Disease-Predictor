# **Predicting Heart Disease Presence Using Clinical Parameters - age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved.**
 #### Mehardeep Singh, Ariana Binarao, Yasmin Faghir, Shadan Namazifard
### **Introduction**
Heart disease encompasses various conditions that affect the heart and blood vessels, including coronary artery disease, which is characterized by the narrowing of the arteries that supply blood to the heart. This narrowing is often caused by various factors, including cholesterol accumulation and heart performance indicators such as the maximum heart rate achieved during stress (American Heart Association, n.d.).

Elevated serum cholesterol levels can lead to the build-up of plaque in the arteries, which may cause atherosclerosis. This condition narrows the arteries and increases the risk of heart attack or stroke. Additionally, age and the type of chest pain experienced by an individual can be indicative of underlying heart conditions. The maximum heart rate an individual can achieve is a reflection of the heart's efficiency and performance, and any significant deviation from the norm could be indicative of heart disease (Mayo Clinic, 2020).

Given this background, our research question is: Can we predict the likelihood of a new patient having heart disease based on their age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved? To tackle this question, we will employ a machine learning approach.

We will be utilizing the Cleveland Heart Disease dataset from the UCI Machine Learning Repository to make our predictions. The dataset includes various clinical parameters, among which we will focus on:

1. **age**: age in years
2. **cp**: type of chest pain
3. **chol**: serum cholesterol in mg/dl
4. **thalach**: maximum heart rate achieved

Our analysis will leverage these parameters to classify patients based on the likelihood of them having heart disease.

### Methods

#### Data Preprocessing and Exploratory Data Analysis

1. Essential libraries were imported, and the Cleveland Heart Disease dataset was obtained from the UCI Machine Learning Repository.

2. The dataset was cleaned and transformed into a tidy format, which involved assigning appropriate data types, handling missing values, and creating a new column 'diagnosis' representing the presence or absence of heart disease.

3. The dataset was split into training and testing subsets. The analysis was conducted exclusively on the training dataset, reserving the testing dataset for the final evaluation of the model.

4. A summary of the training dataset was generated to develop an understanding of the characteristics that the classifier should capture.

5. Used Data visualization to analyze the relationships among age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved, to understand their distributions and relationships.

#### Determining the Optimal Value of 𝑘

The primary objective was to identify the optimal number of nearest neighbors (𝑘) that would yield the highest prediction accuracy. We employed cross-validation to achieve this.

1. The data was centered and scaled using the recipe function to standardize the features.

2. Cross-validation was conducted using ten folds with the vfold_cv function on the training data to minimize bias and to ensure that the model is not overly reliant on a particular subset of the data.

3. A 𝑘-nearest neighbors model was created using a range of 𝑘 values. The recipe and model were integrated into a workflow. The tune_grid function was employed to conduct cross-validation for varying values of 𝑘.

4. The best value of 𝑘 was determined by analyzing the accuracy achieved for different 𝑘 values through graphical representation.


#### Visualizing the Results
To visualize the results we generated a few differnet types of graphs to best undrestand and analyze the data.

1. A scatter plot was generated with maximum heart rate and cholesterol levels as axes, and data points were color-coded based on the diagnosis.

2. A scatter plot comparing Cholesterol level and Resting Blood Pressure. Each point represents an individual from the dataset, and the color of the point indicates whether they have a heart disease diagnosis or not.

3. A scatter plot comparing Cholesterol level and Age. Each point represents an individual from the dataset, and the color of the point indicates whether they have a heart disease diagnosis or not.


4. The trends in the 3 plots were examined. By examining patterns and fluctuations within the dataset, we can gain valuable insights and make informed decisions.This information aids in understanding past performance, predicting future outcomes, and devising strategies accordingly. 

#### Evaluating the Classifier

1. A 𝑘-nearest neighbors model was created using the optimal 𝑘 value. This model, along with the data preprocessing steps, was combined into a workflow and fit to the training dataset.

2. The model’s prediction accuracy was assessed using the testing dataset, which the model had not been exposed to during training.

3. A confusion matrix was generated to evaluate the classifier’s performance concerning different classes and to understand the implications in real-world scenarios.
