# Student Score Test Predicted
To predict student score test (post-test score) in the future.

### About 

The project goal is to get external insight that can potentially affect students' performance on the test results, and if it does, what can we predict based on these results.

## Student Score Test
Student Post-test score is a score test that students get after the learning process has been completed. A post-test is a form of the final evaluation of a lesson.

## Data Understanding


This dataset contains the background of the students and the test results obtained before learning process (pre-test) and after learning process (post-test). 
[Source Data](https://www.kaggle.com/kwadwoofosu/predict-test-scores-of-students)

•	Data Dictionary:

*   **school** - Name of the school the student is enrolled in.
*   **school_setting** - The location of the school.
*   **school_type** - The type of school. Either public or non-public.
*   **classrooom** - The type of classroom.
*   **teaching_method** - Teaching methods: Either experimental or Standard.
*   **n_student** - Number of students in the class.
*   **student_id** - A unique ID for each student.
*   **gender** - The gender of the students: male or female.
*   **lunch** - Whether a student qualifies for free/subsidized lunch or not.
*   **pretest** - The pretest score of the students out of 100

## Data preparation
•	Code Used : Python (Google Colab Studio)

•	Packages : caTools, ggplot2

## Modeling Flow : 
### 1. Split Data : train – test
   Split data into training data and testing data
### 2. Fit the model on training data
   Build and train the model on the training data using lm() function
### 3. Model Diagnostic
  
 Interpret and pre-evaluate the model
  
 -Model's Summary
 
![image](https://user-images.githubusercontent.com/88583319/129440584-9391de80-0c4b-4f73-9e97-683233343626.png)

  The model with an adjusted R-square value of 0.6225. The adjusted R-square value indicates that 62.25% total variation of PremiumPrice can be explained by all the features.
  
 - Model's Residual Diagnostic
    
   • 	Residual Plot
   
![image](https://user-images.githubusercontent.com/88583319/129440603-39c9c9ee-a2f0-4d4c-9805-05f95f4518a9.png)
   
 The model diagnostic plots above show that the linear regression model fits the data well. There is a straight-line relationship between the residual and the fitted_value, residuals have a constant variance, and residuals are normally distributed.
    
### 4. Predict Data
   Using the trained model to predict test data using predict()
   
![image](https://user-images.githubusercontent.com/88583319/129440630-6fda68ca-bba6-4ad7-8c16-a02f67c27ccb.png)
   
### 5. Evaluate The Model
   Evaluate the model on test data using MAE and MAPE
   
The model with Mean Absolute Error (MAE) value is 2624.7 and the Mean Absolute Percentage Error (MAPE) value is 0.1160156. 
On averange, our prediction deviates the true Premium Price by 2624.7. Moreover, this 2624.7 is equivalent to 12% deviation relative to the true Premium Price.

# Summary

Based on the linear regression model, the Mean Absolute Error (MAE) value is 2624.7 and the Mean Absolute Percentage Error (MAPE) value is 0.1160156. On averange, our prediction deviates the true Premium Price by 2624.7. Moreover, this 2624.7 is equivalent to 12% deviation relative to the true Premium Price.The MAPE value is 12% indicates that the prediction results are accurate and can be used to estimate premium prices in the following year. 
