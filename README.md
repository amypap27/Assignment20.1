# Assignment20.1

### Capstone: Initial Report &amp; EDA

**Amy Papandreou**

#### Link to Jupyter Notebook
Here is my Jupyter Notebook

#### Executive summary
The goal of this project is to use available student data (including demographic data, socio-economic data, and prior academic performance) to predict whether students will ultimately graduate or drop out from their university program.

#### Rationale
This question is important for a number of reasons. A lot of effort is spent by students in the college application and preparation process. This includes not only high school coursework, activities, and standardized test prep, but also all of the hours spent researching and visiting schools and completing college applications. Similarly, colleges also invest a lot of effort in selecting their incoming class. These days they receive an enormous number of applications that they have to read through, discuss, and select from.  In many cases, they also spend money and effort to encourage students to accept their admissions offer. However, despite all of this time and effort spent by both parties, there are still many students that drop out or leave their university before graduating. While there will always be a handful of students with truly extenuating circumstances, this is an enormous opportunity cost.  If a model could be built to identify students who are most at risk of dropping out, then perhaps universities could add additional resources or support programs to target these "at-risk" students and increase the likelihood that more of them will graduate instead.

#### Research Question
Predict whether a student will graduate or drop out of college based on available student data, including demographic data, socioeconomic data, and prior academic performance.

#### Data Sources
The dataset is from kaggle.
https://www.kaggle.com/datasets/thedevastator/higher-education-predictors-of-student-retention/data

#### Initial EDA
Before building any models, I did some initial exploration of the dataset. The dataset itself was clean, with no null values that needed to be resolved. 
Initially the dataset contained 3 values in the Target column: Graduated, Dropout, and Enrolled.  Since the Enrolled students might ultimately either graduate or dropout, their final status is undetermined.  I therefore dropped these students from the dataset so that I could focus my classification task on predicting dropout vs graduated.
I also did some initial data exploration and discovered certain features that seem to have some potential differentiation between graduated/dropout students.  The details are shown in the graphs and discussed in the Jupyter notebook.  However, in building my models I retained all of the available features.

#### Methodology
This is a classification task - I am trying to predict whether student outcomes are "Graduated" or "Dropped Out".
As such, I plan to use a variety of the classification methods that we have learned so far.  Some of the model types that I plan to try are: KNN, Logistic Regression, Decision Trees, and SVM.

I plan to focus on accuracy of the various models to compare them but also on their precision. It seems important that we minimize the number of false positives (i.e. students who we predict will graduate but actually drop out). If there is a way to better support students who might drop out and instead help them successfuly graduate, then we need to make sure we can accurately identify the students who are at risk of dropping out so that we know who to help.

After creating some initial versions of these models using default parameters, I plan to try to tune the hyperparameters using GridSearchCV to further improve the models. 
As we learn new models in the coming weeks, I may be able to expand this list.  More specifically, based on the material we just studied in Module 20, I plan to also try using an ensemble model.

#### Results
So far I have built and tested the following models: Logistic Regression, KNN, Decision Trees and SVM.  I initially built models with default hyperparameters and found that Logistic Regression performed the best, with an accuracy of 0.908 and precision of 0.915 on the test dataset.  The Decision Tree model with default hyperparameters definitely seemed to be overfit.

I also tried tuning the hyperparameters of these models a bit using GridSearchCV.  While Logistic Regression did not improve much this way, I was able to improve the Decision Tree and SVM models a bit.

Based on my initial data exploration, as well as Linear Regression Coefficients, it seems that some of the important factors in predicting graduation vs dropping out are: tuition fees being up to date, scholarships, international students, and curricular units approved during the 1st and 2nd semesters.
The Decision Tree also listed 2nd semester curricular units approved and tuition fees up to date as its 2 most important features.

#### Next steps
I have a few planned next steps:
1) Based on what we just learned in Module 20, I want to try building an ensemble model to see if I can improve my performance.
2) Although the dataset came with categorical columns encoded as numbers, the numerical values are arbitary (i.e. they are not ordered from low to high in any meaningful way but just seem to be mapped arbitrarily to integer values.)  I want to try using one-hot encoding to split these into separate columns to see if that improves the models.
3) I am also noticing that the features in my dataset are a mixture of features that would be available when a student first enrolls (such as marital status, gender, age, nationality, parent's occupations) and features that are not available until after enrollment (such as the 1st semester and 2nd semester columns).  I am curious whether the after-enrollment features are a critical component of predicting student graduation/dropout, or whether this can be predicted with just features available at the time of enrollment. 


##### Contact and Further Information



