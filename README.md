# ANA-505-Week-6-activity

1. SVM Algorithm dataset:
 
The Iris dataset is one of the most iconic datasets in statistics and machine learning. It was introduced by the British statistician and biologist Ronald Fisher 
in his 1936 paper as an example of linear discriminant analysis.
Sources: 
https://thedatafrog.com/en/articles/visualizing-datasets/
https://rpubs.com/ben_n/Iris_Dataset

SVM algorithm that is used here is "support vector machine (SVM) learns a hyperplane to classify data into 2 classes. At a high-level, SVM performs a similar task 
like C4.5 except SVM doesn’t use decision trees at all." - https://hackerbits.com/data/top-10-data-mining-algorithms-in-plain-english/

This is confusion matrix for this dataset after running SVM:
                    Actual
Predicted    setosa versicolor virginica
  setosa         50          0         0
  versicolor      0         48         2
  virginica       0          2        48 
Accuracy Rate= Total predictions / Total correct predictions
Therefore, based on this confusion matrix, the accuracy rate of the predictions is: 97.33%

2. K means algorithm:
Same Iris dataset, but algorithm is different. 
K-means algorithm is "creates k groups from a set of objects so that the members of a group are more similar. It’s a popular cluster analysis technique for exploring a dataset." - https://hackerbits.com/data/top-10-data-mining-algorithms-in-plain-english/
This is summary statistics of dataset:
------------------------------------
> summary(iris)
  Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500  
       Species  
 setosa    :50  
 versicolor:50  
 virginica :50  
------------------------------------------
This is confusion matrix that reflects accuracy of predictions:
   iris.class
    setosa versicolor virginica
  1      0          3        36
  2     50          0         0
  3      0         47        14
Accuracy Rate= Total predictions / Total correct predictions
Accuracy Rate = 61 / 150 = 0.4067
Therefore, based on this confusion matrix, the accuracy rate of the predictions is:  40.67%

3. C50 algorithm:
This is the same Iris dataset, but new algorithm C50 is used. 
C50 algorithm is "has become the industry standatd for producing decision trees, because it does well fo rmost types of problems directly out of the box. Compared to more advanced and sophisticated machine learning mnodels (e.g. Neural Networks and Support Vector Machines), the decision trees under the C5.0 algorithm generally perform nearly as well but are much easier to understan and deploy." - https://rpubs.com/cyobero/C50
> head(iris,4)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
> dim(iris)
[1] 150   5
The model based on training data and C.50 algorithm:
(testData$Species == predict(dtModel, testData))
 [1]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
[13]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
[25]  TRUE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE FALSE
[37]  TRUE  TRUE  TRUE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE
> 
> mean(testData$Species == predict(dtModel, testData))
[1] 0.9333333
Cell Contents
|-------------------------|
|                       N |
|         N / Table Total |
|-------------------------|
Total Observations in Table:  45 
 
          |     FALSE |      TRUE | 
          |-----------|-----------|
          |         3 |        42 | 
          |     0.067 |     0.933 | 
          |-----------|-----------|
Based on this confusion matrix, the accuracy rate of the predictions is: 93.3%. 
In this representation the accuracy rate is self-obvious from the chart without the need for further calculations.
