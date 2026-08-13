Linear regression models assume that the response $Y$ is quantitative, but in many situations, the response variable is instead *qualitative* or *categorical*. Predicting a qualitative response for an observation can be reffered to as *classifying* that obsevation.
Just as in the regression setting, in classification we have a set of training observations $(x_{1},y_{1}),(x_{2},y_{2}),\dots,(x_{n},y_{})$ that we can use to build a ***classifier***.

This section covers some classifiers such as [[LogisticRegression|logistic regression]], linear discriminant analysis, quadratic disciminant analysis, naive Bayes, and [[KNN|K-nearest neighbors]].
There's other more computer-intensive classification methods such as trees, random forests, boosting, support vector machines and neural networks, but covered in other chapters.

#### Why not linear regression?
Why isn't linear regression appropiate in the case of a qualitative response? 
In order to perform linear regression with a categorical response, we would need to assign some numerical value to each category, and the problem is that, depending on the values we choose, we would end up with completely different linear models. 
In general, linear regression completely fails when it comes to problems with more than two categories, although for a binary response, we could assign the values 0 and 1, but later we'll see that the predictions made with this method will be the same as with a linear discriminant analysis (LDA).


#ISLP #statistics #ML #classification 