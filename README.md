
                                           #Overview of Project
                                           
In this project, we are analyzing the credit card risk dataset from LendingClub. Credit card risk consists of unbalanced classes. We utilized imbalanced-learn and scikit-learn libraries to train and evaluate models using resampling. To oversample the dataset, we used RandomOverSampler and SMOTE algorithms, undersampling; we used ClusterCentroids and combinational over and under sampling using  SMOTEENN algorithms. To predict credit card risk, we used two machine learning models, BalancedRandomForestClassifier and EasyEnsembleClassifier, which helped to reduce bias.

                                               #Results                              

We split 75% of the dataset as training and 25% of the same dataset as testing. 

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/spliting.png)  

•	Training: Low Risk=51366, High Risk= 246 
•	Test: Low Risk=17104, High Risk=101

#Oversample

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/d12_accuracy.png)       
![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/d12_report.png)       

Random oversample: random oversample randomly duplicates from minority classes to address the class imbalance issue.      

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/counter_random.png)       
As we can see the count of both High and Low Risk is 51366.
Balanced Accuracy score is 67.4%
Precision for High Risk is 1%, and recall is 70%
Precision for Low Risk is 100%, and recall is 65%

SMOTE: Synthetic Minority Over-sampling Technique duplicates closest neighbors in the minority class.

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/counter_random.png)  
The Count of both High and Low Risk is 51366.
Balanced accuracy score is 66.2%
Precision for High Risk is 1%, and recall is 63%
Precision for Low Risk is 100%, and recall is 69%

#Undersample

ClusterCentroids Model: Majority class gets undersampled or decreased to the minority class. The algorithm targets the majority class and generates synthetic data points called centroids representing the clusters. 

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/cc_counter.png)
The count of both High and low risk is 246.
Balanced accuracy score is 54.4%
Precision for High Risk is 1%, and recall is 69%
Precision for Low Risk is 100%, and recall is 39%


SMOTEEN: Synthetic Minority Oversampling Technique + Edited NearestNeighbors, both oversample and undersample, are executed. Oversample with SMOTE algorithm and clean the resulting data with undersampling. Two nearest neighbors belong to two different classes then data is dropped. 

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/smoteen_counter.png)
The count of High Risk is 68460, and the low risk is 62011.
Balanced Accuracy score is 64.7%
Precision for High Risk is 1%, and recall is 72%
Precision for Low Risk is 100%, and recall is 57%

Two machine learning models, BalancedRandomForestClassifier and EasyEnsembleClassifier, are used to predict credit card risk and to help reduce bias.

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/d3_accuracy.png)

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/d3_report.png)

BalancedRandomForestClassifier: randomly undersamples each bootstrap sample while an estimated number of trees in the forest.

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/counter_random.png)
As we can see count of both High and Low Risk is 51366.
balanced accuracy score is 93.1%
precision for High Risk is 3%, and recall is 70%
precision for Low Risk is 100%, and recall is 87%

EasyEnsembleClassifier: Ensemble learning combines multiple machine learning algorithms,  selects a random subset, and makes an ensemble of different settings. It decreases the variance of the model and increases overall performance. 

![](https://github.com/smzd/Credit_Card_Analysis/blob/main/Resources/counter_random.png)
As we can see count of both High and Low is 51366.
balanced accuracy score is 67.4%
precision for High Risk is 9%, and recall is 92%
precision for Low Risk is 100%, and recall is 94%

                                                 #Summary

We must consider that the credit card risk data set has 99% low-risk and 1% high-risk applications. This may skew the result since high-risk application data is deficient when algorithms create classes via over and under-sampling.

Based on the calculation, we can conclude that the EasyEnsembleClassifier algorithm had the highest accuracy of 93% in predicting high-risk loan status. The result indicating low-risk loan status was also more precise. Therefore we can conclude that the EasyEnsembleClassifier algorithm is the best solution for our analysis to perform credit card risk prediction.

Let's summarize all six high risk application results:

•	EasyEnsembleClassifer: 93% accuracy, 9% precision, 92% recall, and 16% F1 Score

•	BalancedRandomForestClassifer: 78.9% accuracy, 3% precision, 70% recall and 6% F1 Score

•	SMOTE: 66.2% accuracy, 1% precision, 63% recall and 2% F1 Score

•	RandomOverSampler: 67.4% accuracy, 1% precision, 70% recall and 2% F1 Score

•	SMOTEENN: 64.7% accuracy, 1% precision, 72% recall and 2% F1 Score

•	ClusterCentroids: 54.4% accuracy, 1% precision, 69% recall and 1% F1 Score

