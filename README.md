# Student Score Test Predicted
To predict student score test (post-test score) in following time.

### About 

The project goal is to get external insight that can potentially affect students' performance on the test results, and if it does, what can we predict based on these results.

## Student Score Test
Student score test (post-test score) is a score test that students get after the learning process has been completed. A post-test is a form of the final evaluation of a lesson.

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

## Modeling Flow : 

### 1. Data Preparation

 We use Google Colab to build the student's score prediction model. First, we explore the data, find missing and duplicate values, and then drop a few columns that do not affect to our model. Last, we do categorical encoding and find correlation between variables.
 
 ![image](https://beeimg.com/images/u76128354922.png)
 
We can see there is a really good correlation between pre-test scores and post-test scores. We don't find any multicollinearity
 
### 2. Split Data
 Split data into training data and testing data:
 
Training data : 70%
Testing data : 30%
 
### 3. Build Model on Training Data
  
 Interpret and pre-evaluate the model
  
 - Pre-evaluate model
 
![image](https://beeimg.com/images/i28440240472.png)

we see the R-squared is 0.904. Meaning, pre-test scores explain 90,4% of the variability in post-test scores using OLS Regression Results.
  
![image](https://beeimg.com/images/g18245817892.png)
when we add in all other variables in a multiple regression, we conclude that school type & gender are not a very good predictors of post-test score based on their p-values that indicate a weak association. We drop them to our model. And then, we create Linear Regression.
    
### 4. Evaluate the Model
   Evaluate the model on test data using Explained Variance and MAE. We get 94.76% of Explained Variance and MAE value is 2.52
 
   
### 5. Compare Multiple Model
- Lasso Regression          : Explained Variance: 92.55%, MAE: 3.04
- Decision Tree Regression  : Explained Variance: 92.20%, MAE: 3.07
- Support Vector Regression : Explained Variance: 91.11%, MAE: 3.36
- Random Forest Regression  : Explained Variance: 94.24%, MAE: 2.65
- Neural Network Regression : Explained Variance: 94.70%, MAE: 2.89

# Summary

According to 6 models above, Linear Regression model has the highest Explained Variance: 94.76% and the smallest MAE: 2.52, that the prediction results are accurate and can be used to estimate student score test in following time.
