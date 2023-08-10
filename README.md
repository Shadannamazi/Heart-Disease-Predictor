{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "05bb7b42-e0e7-40cf-871f-ce9ca5429048",
   "metadata": {},
   "source": [
    
    "# **Predicting Heart Disease Presence Using Clinical Parameters - age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved.**\n",
    " #### Mehardeep Singh, Ariana Binarao, Yasmin Faghir, Shadan Namazifard"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "04140995-08b5-4140-8fde-646f0158a70f",
   "metadata": {},
   "source": [
    "### **Introduction**\n",
    "Heart disease encompasses various conditions that affect the heart and blood vessels, including coronary artery disease, which is characterized by the narrowing of the arteries that supply blood to the heart. This narrowing is often caused by various factors, including cholesterol accumulation and heart performance indicators such as the maximum heart rate achieved during stress (American Heart Association, n.d.).\n",
    "\n",
    "Elevated serum cholesterol levels can lead to the build-up of plaque in the arteries, which may cause atherosclerosis. This condition narrows the arteries and increases the risk of heart attack or stroke. Additionally, age and the type of chest pain experienced by an individual can be indicative of underlying heart conditions. The maximum heart rate an individual can achieve is a reflection of the heart's efficiency and performance, and any significant deviation from the norm could be indicative of heart disease (Mayo Clinic, 2020).\n",
    "\n",
    "Given this background, our research question is: Can we predict the likelihood of a new patient having heart disease based on their age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved? To tackle this question, we will employ a machine learning approach.\n",
    "\n",
    "We will be utilizing the Cleveland Heart Disease dataset from the UCI Machine Learning Repository to make our predictions. The dataset includes various clinical parameters, among which we will focus on:\n",
    "\n",
    "1. **age**: age in years\n",
    "2. **cp**: type of chest pain\n",
    "3. **chol**: serum cholesterol in mg/dl\n",
    "4. **thalach**: maximum heart rate achieved\n",
    "\n",
    "Our analysis will leverage these parameters to classify patients based on the likelihood of them having heart disease.\n",
    "\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "7ab4c6a8-a03c-48e5-a80f-6a078ecd729f",
   "metadata": {
    "tags": []
   },
   "source": [
    "### Methods\n",
    "\n",
    "#### Data Preprocessing and Exploratory Data Analysis\n",
    "\n",
    "1. Essential libraries were imported, and the Cleveland Heart Disease dataset was obtained from the UCI Machine Learning Repository.\n",
    "\n",
    "2. The dataset was cleaned and transformed into a tidy format, which involved assigning appropriate data types, handling missing values, and creating a new column 'diagnosis' representing the presence or absence of heart disease.\n",
    "\n",
    "3. The dataset was split into training and testing subsets. The analysis was conducted exclusively on the training dataset, reserving the testing dataset for the final evaluation of the model.\n",
    "\n",
    "4. A summary of the training dataset was generated to develop an understanding of the characteristics that the classifier should capture.\n",
    "\n",
    "5. Used Data visualization to analyze the relationships among age, type of chest pain, serum cholesterol levels, and maximum heart rate achieved, to understand their distributions and relationships.\n",
    "\n",
    "#### Determining the Optimal Value of 𝑘\n",
    "\n",
    "The primary objective was to identify the optimal number of nearest neighbors (𝑘) that would yield the highest prediction accuracy. We employed cross-validation to achieve this.\n",
    "\n",
    "1. The data was centered and scaled using the recipe function to standardize the features.\n",
    "\n",
    "2. Cross-validation was conducted using ten folds with the vfold_cv function on the training data to minimize bias and to ensure that the model is not overly reliant on a particular subset of the data.\n",
    "\n",
    "3. A 𝑘-nearest neighbors model was created using a range of 𝑘 values. The recipe and model were integrated into a workflow. The tune_grid function was employed to conduct cross-validation for varying values of 𝑘.\n",
    "\n",
    "4. The best value of 𝑘 was determined by analyzing the accuracy achieved for different 𝑘 values through graphical representation.\n",
    "\n",
    "\n",
    "#### Visualizing the Results\n",
    "To visualize the results we generated a few differnet types of graphs to best undrestand and analyze the data.\n",
    "\n",
    "1. A scatter plot was generated with maximum heart rate and cholesterol levels as axes, and data points were color-coded based on the diagnosis.\n",
    "\n",
    "2. A scatter plot comparing Cholesterol level and Resting Blood Pressure. Each point represents an individual from the dataset, and the color of the point indicates whether they have a heart disease diagnosis or not.\n",
    "\n",
    "3. A scatter plot comparing Cholesterol level and Age. Each point represents an individual from the dataset, and the color of the point indicates whether they have a heart disease diagnosis or not.\n",
    "\n",
    "\n",
    "4. The trends in the 3 plots were examined. By examining patterns and fluctuations within the dataset, we can gain valuable insights and make informed decisions.This information aids in understanding past performance, predicting future outcomes, and devising strategies accordingly. \n",
    "\n",
    "#### Evaluating the Classifier\n",
    "\n",
    "1. A 𝑘-nearest neighbors model was created using the optimal 𝑘 value. This model, along with the data preprocessing steps, was combined into a workflow and fit to the training dataset.\n",
    "\n",
    "2. The model’s prediction accuracy was assessed using the testing dataset, which the model had not been exposed to during training.\n",
    "\n",
    "3. A confusion matrix was generated to evaluate the classifier’s performance concerning different classes and to understand the implications in real-world scenarios.\n"
   ]
  },
  
