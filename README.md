# Simple Guide to k-Fold Cross Validation
A simple code for beginners to learn to use k-fold cross validation to reduce biasedness when doing classification

# Project Aim
For people starting out to do machine learning, there are many ways to help to improve their model. This project aims to provide a simple usage to k-fold cross validation to help beginners to understand how cross-validation works.

# Methodology
1. Our data will be the Breast Cancer dataset from Sklearn's datasets where X contains features for each instances and y is their class
2. We will first explore the dataset to see how many are malignant (labelled as 0) and how many are benign (labelled as 1)
3. We will then initialise a Logistic Regression Model which will be used to aid in our classification
4. We then set the number of splits (k) to be 5, hence we are using 5-fold cross validation in our method
5. We will then find the accuracy and F1 score (where positive label is set to 1 for simplicity) at each of the fold and store them in a list
6. F1 score is calculated in addition to accuracy because the dataset is a bit unbalanced (212 malignant, 357 benign) so as to provide a better measurement for the model's performance
7. The accuracy and F1 score for each of the 5 folds are plotted
8. The accuracy and F1 score are then averaged across the 5 folds

# Explaination for step 4 (5-fold cross validation)
1. For k-fold cross validation, the entire dataset X will be split into k subsets known as folds.
2. In our project, since our k is 5, the the entire dataset X will be split into 5 folds.
3. This split will be random if shuffle is set to True and consecutive if shuffle is set to False
4. In the first iteration, 1 of the 5 (or k) folds will be used as the test set and the remaining 4 out of the 5 folds will be used for training the classifier
5. In the second iteration, 1 of the 5 (or k) folds that was has not been used as the test set will be used as the test set and the remaining 4 (or k - 1) out of the 5 (or k) folds will be used for training the classifier
6. There will be a total of 5 (or k) iterations where in each iteration, the test set will be a different fold from each iteration.
7. So in total, the model will have a chance to be trained on different parts of the dataset to do classification and this will help to reduce biasedness

# Conclusion
The model we have created is able to classify with an average accuracy of 95.3% and an average F1 score of 96.3% which is pretty good. Keep in mind, these two values have been averaged across 5-folds instead of just taking from a single fold. This will help to prevent some biasedness which will be encountered if only a one time train test split is used. 

I hope that through understanding this simple usage of k-fold cross validation, it can help in reducing your model's biasedness. Thank you.
