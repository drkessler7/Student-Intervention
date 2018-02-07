## Student Intervention

### Overview

Higher education plays an essential role in opening career opportunities to individuals and providing better products and services to society. Today, education heavily relies on technology, and so large amounts of student data have become available. More and more institutions are using learning management systems to capture data like student activity logs, grades, and interactions. Using this data, schools may develop systems to help increase student engagement and success in many ways.

As an engineer who places a huge value on all forms and levels of education, this project means something special to me. I strive to stay up-to-date with the latest tools and trends, and so I completed this supervised learning project as part of a continuing education program at Udacity. 

### Problem
A school district has the goal of reaching a 95% graduation rate by the end of the decade. Students who are in danger of dropping out need to be identified so that the proper support can be given to them. The task for this project is to find the most effective model that uses the least amount of computational resources to save on the budget. I analyze a dataset of former students’ performance and develop a model that predicts the likelihood that a given student will pass, quantifying whether it is necessary to intervene with that student.

### Process

#### Data Source
The student data for this project is provided by Udacity. 

#### Data Description
The data  consists of a single .csv file that contains information for 395 former students that were enrolled in the school district. There are 31 attributes given for each student.These features contain a mixture of numerical and categorical values. Some of the features include: age, sex, if they have internet access at home, how much they go out with friends, and if they are in a romantic relationship. 

#### Data Exploration
First, I look at the number of students who passed and the number who failed, to see that only 67% of the students graduated on time. Then I look at the features to see if there are values that are non-numeric. Machine learning algorithms expect data to be in numerical format, so if there are categorical or yes/no values, they will need to be transformed into something more useful.

#### Data Preprocessing
I convert the non-numerical features into numerical features by creating more ‘dummy’ features. These are the result of splitting one existing feature into multiple new ones. For example, the ‘sex’ feature can be replaced with ‘sex_M’ and ‘sex_F’, so that instead of a males student’s ‘sex’ being ‘M’, their ‘sex_M’ will be 1, and their ‘sex_F’ will be 0. Dummy features are made for all features that contain non-numerical values. 

Next I split the dataset so that the data for 300 students will be used to train a machine learning model, and the remaining data will be used to test it. In order to make more robust models, it is important to train and test machine learning models on different data.

#### Supervised ML Algorithms
The data for each student includes whether or not the student passed, and this ‘label’ is the value that we will need to predict for future students. Since we have labeled data, and the labels are categorical values, we know this is a supervised classification problem. I consider three different machine learning algorithms for this project: Support Vector Classifier (SVC), Artificial Neural Network (ANN), and the Decision Tree Classifier.

I look at the data and consider the advantages and disadvantages of each algorithm. To better see the performance of each model, I train each of them and compare their F1 scores and the times it takes to execute each of the models. F1 scores show the accuracy of classification models where the labels only have two possible values (yes/no in this case).

#### Model Choice
The SVC provides the best F1 score out of the three models that I try. However, it takes the longest to run. If the school has to make predictions for millions of students, then perhaps one of the other models should be chosen. However, it can be reasonably assumed that the number of predictions needed will be much smaller, and so the SVC is used. It has an F1 score of 0.8462, which means that it correctly predicts whether or not a student will pass 84.62% of the time.

#### Model Improvement
The Support Vector Classifier algorithm has parameters built into it that I tune to help improve the accuracy of the predictions. I try different values for that parameters using ‘grid search’. This method takes ranges of values for the parameters and tries all of the different combinations. The final model uses the parameters that yield the best results. This tuned model makes correct predictions 86.09% of the time.

#### Conclusion
By using this classification model, the school can better see which students are at risk of not graduating on time. The school may then offer additional support to those students to make sure they get back on the right path. Within several years of beginning this new program, the school will likely reach its goal of 95% graduation rate. 

## About Files/Folders in this Repository
* ‘student_intervention.ipynb’: This Jupyter Notebook explains the in-depth reasoning behind all of the steps that I take in completing this project. It contains Python code cells that can be run individually, as well as markdown cells that only contain text to explain the each of the steps. 

* ‘student_intervention.html’: This html file’s contents are the same as those of the ‘student_intervention.ipynb’ notebook, and can be opened in a web browser. 

* ‘Student Intervention Images’: This folder contains screenshots of various images and charts created by this notebook. 

* ‘Student Intervention Starter Files’: This folder contains the files provided by Udacity to start this project.

## Installation
The installation documentation for the Jupyter platform can be found [here](https://jupyter.readthedocs.io/en/latest/install.html).

Documentation for advanced usage of Jupyter notebook can be found [here](https://jupyter-notebook.readthedocs.io/en/latest/).

This project requires **Python 2.7** and the following Python libraries installed:
* [numpy](http://www.numpy.org/)
* [pandas](http://pandas.pydata.org)
* [scikit-learn](http://scikit-learn.org/stable/)

To run locally on your machine, launch from a command prompt with:
 
     $ jupyter notebook
