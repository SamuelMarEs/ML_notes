In [[AssessingModelAccuracy|assessing model accuracy]], the *MSE* was covered, but only for regression settings. Now, instead of a quantitative problem, let's say we have a quantitative problem. Suppose we have $\{(x_{1},y_{1}),(x_{2},y_{2}),\dots,(x_{n},y_{n})\}$, where $y_{1},\dots,y_{n}$ are qualitative. The most common approach to determine accuracy is the *training error rate*, the proportion of mistakes if we apply $\hat{f}$ to the training observations: 
$$
	\frac{1}{n}\sum_{i=1}^{n}I(y_{i}\neq \hat{y}_{i}),
$$
where $\hat{y_{i}}$ is the predicted label for the $i$-th observation, and $I=\begin{cases}1,\quad\text{if}\quad y_{i}\neq \hat{y_{i}}\\ 0,\quad\text{if}\quad y_{i}= \hat{y_{i}}\end{cases}$.
In the same way we can define the *test error rate* for unseen observations $(x_{0},y_{0})$.

### Bayes Classifier
The test error rate is minimized by assigning each observation to its most likely class given the predictor values. In other words, we want to assign the observation $x_{0}$ to the class $j$ for which 
$$
	P(Y=j|X=x_{0})
$$
is largest. This way of classifying data is called the *Bayes classifier*.
It produces the lowest possible test error rate, called the *Bayes error rate*, and since it chooses the class with higher probability, this error rate for a predictor $x_{0}$ is 
$$
	1-E(\max_{j}(P(Y=j|X=x_{0}))).
$$
In theory, this is the best classifier. But in reality, we don´t know the conditional distribution of $Y$ given $X$, so the Bayes classifier is only theoretical. One alternative is the [[KNN|K Nearest Neighbors]] (KNN) classifier, which attempts to estimate the distribution of $Y$ given $X$.


Both regression and classification problems share that there's no real strong relationship between training and test error, which is why there's he concept of the *bias-variance tradeoff*.

#statistics #error #mean #probability #classification
