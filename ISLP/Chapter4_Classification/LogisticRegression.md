Consider a set of data where the response falls into one of two categories, *Yes* or *No* (or 1 and 0). Logistic regression models the *probability* that $Y$ belongs to a particular category.
This probability can be written as 
$$
	P(Y=\text{Yes}|X),
$$
which we abbreviate $p(X)$, and will range between 0 and 1. Then, given a particular $x\in X$, we can give a prediction for $Y$ given $p(x)$.

### The Logistic Model
How sould one model the relationship between $p(X)=P(Y=1|X)$ and $X$? If we were to try to fit a linear model of the form $p(X)=\beta_{0}+\beta_{1}X$, we would have values for $p(X)$ outside of the range $[0,1]$. To avoid this, we have to use a function that gives outputs between 0 and 1 for all values of $X$. In logistic regression, we use the ***logistic function***, 
$$
	p(X)=\frac{e^{ \beta_{0}+\beta_{1}X }}{1
	+ e^{ \beta_{0}+\beta_{1}X }}.
$$
To fit this model, we use a method called ***maximum likelihood***, discussed later.
The logistic function produces an S-shaped curve 
![[LogisticFunction.png|694]]
A bit of manipulation is enough to show that 
$$
	\frac{p(X)}{1-p(X)}=e^{ \beta_{0}+\beta_{1}X }.
$$
The quantity to the left $\frac{p(X)}{1-p(X)}$ is called the ***odds***, and can take on any value in the range $[0,\infty)$, which indicate very low and very high probability, respectively. 
Taking the natural logarithm of both sides we obtain 
$$
	\ln\left( \frac{p(X)}{1-p(X)} \right)=\beta_{0}+\beta_{1}X.
$$
The left-hand side is called the ***log odds*** or *logit*. Thus, we see that the logistic regression model has a logit that is linear in $X$.

Aditionaly, we can use the same approach of dummy variables as in the linear regression setting to work with [[QualitativePredictors|qualitative predictors]].

### Estimating the Regression Coefficients
In order to estimate $\beta_{0}$ and $\beta_{1}$ based on the available training data, the most general method used is the method of *maximum likelihood*. The basic intuition behind using maximum likelihood is as follows: we seek estimate for $\beta_{0}$ and $\beta_{1}$ such that the predicted probability $\hat{p}(x_{i})$  corresponds as closely as possible to the actual category of $x_{i}$. In other words, we want to find $\hat{\beta_{0}}$ and $\hat{\beta_{1}}$ such that $p(X)$ yields a number close to one for all $x_{i}$'s who's category is labeled *Yes* (or 1). This is formalized using what's called a ***likelihood function***: 
$$
	\ell(\beta_{0},\beta_{1})=\prod_{i:y_{i}=1}p(x_{i})\prod_{i':y_{i}'=0}(1-p(x_{i'})).
$$
The estimates $\hat{\beta}_{0}$ and $\hat{\beta}_{1}$ are chosen to **maximize** this likelihood function. This method is used to fit many other non-linear models, and the [[OLS|least squares]] approach for [[MultipleLinearRegression|linear regression]] is actually a special case of maximum likelihood. 
Just as with [[SimpleLinearRegression|linear regression]], we can measure the the accuracy of the coefficient estimates by computing their standard errors ($SE$), and use what is called a $z$-statistic, which plays the same role as the $t$-statistic in linear regression, and can be used to accept or reject the null hypothesis $H_{0}:\beta_{1}=0$ based on a $p$-value.

Once the coefficients have been estimated, we can compute the probability of $Y=\text{yes}$ for any given $x_{i}$. That is $\hat{p}(x_{i})$, and if $\hat{p}(x_{i})>0.5$ then we set our predicted category to be *Yes*, and otherwise it is *No*.

### Multiple Logistic Regression
Now let's consider the problem of predicting a binary response using multiple predictors. We can generalize the logistic model using the *log odds* as follows: 
$$
	\ln\left( \frac{p(X)}{1-p(X)} \right)=\beta_{0}+\beta_{1}X_{1}+\dots+\beta_{p}X_{p},
$$
where $X=(X_{1},\dots, X_{p})$ are $p$ predictors. We could also write 
$$
	p(X)=\frac{e^{ \beta_{0}+\beta_{1}X_{1}+\dots+\beta_{p}X_{p} }}{1+e^{ \beta_{0}+\beta_{1}X_{1}+\dots+\beta_{p}X_{p} }}.
$$
Once again, we use the *maximum likelihood* method to estimate the coefficients $\beta_{0}, \beta_{1}, \dots \beta_{p}$.

### Multinomial Logistic Regression
The previous sections cover the case in which we have a binary response. But sometimes we wish to classify a response variable that has more than two classes. 
It is possible to extend the two-class logistic regression approach to the setting of $K > 2$ classes. This extension is what is sometimes called as ***multinomial logistic regression***. 
First we select a single class o serve as the ***baseline***; without loss of generality, we select the $K$-th class for this role. Then we use the new model 
$$
	P(Y=k|X=x)=\frac{e^{ \beta_{k 0}+\beta_{k 1}x_{1}+\dots+\beta_{kp}x_{p}}}{1+\sum_{l=1}^{K-1}e^{ \beta_{l 0}+\beta_{l 1}x_{1}+\dots+\beta_{lp}x_{p} }},
$$
for $k=1,\dots,K-1$, and 
$$
	P(Y=K|X=x)=\frac{1}{1+\sum_{l=1}^{K-1}e^{ \beta_{l 0}+\beta_{l 1}x_{1}+\dots+\beta_{lp}x_{p} }}.
$$
It is possible to show that for $k=1,\dots,K-1$, 
$$
	\ln\left( \frac{P(Y=k|X=x)}{P(Y=K|X=x)} \right)=e^{ \beta_{k 0}+\beta_{k 1}x_{1}+\dots+\beta_{kp}x_{p}}.
$$
This equation is the *log odds* between any pair of classes, and once again we have that it's linear. 
The decision of which class to choose as the baseline is unimportant. The coefficient estiamtes will differ between different models that use a different class as baseline, but the fitted values (predictions), log odds between any pair of classes, and the other key model outputs will remain the same. Nonetheless, interpretation of the coefficients in a multinomial logistic regression model must be done with care, since they are tied to the choice of baseline.

#### Softmax coding
There exists an alternative coding for multinomial logistic regression, known as the ***softmax*** coding. It is used extensively in some areas of machine learning literature, although the fitted values (predictions), log odds between any pair of classes, and other key outputs remain the same. In the softmax coding, instead of choosing a baseline, all clases $K$ are treated symmetrically, and assume that for $k=1,\dots,K$, 
$$
	P(Y=k|X=x)=\frac{e^{ \beta_{k 0}+\beta_{k 1}x_{1}+\dots+\beta_{kp}x_{p}}}{\sum_{l=1}^{K}e^{ \beta_{l 0}+\beta_{l 1}x_{1}+\dots+\beta_{lp}x_{p}}}.
$$
Thus, we are estimating the coefficients for all $K$ classes, instead of just for $K-1$ classes. We can also compute the log odds ratio between any two clases as 
$$
	\ln\left( \frac{P(Y=k|X=x)}{P(Y=k'|X=x)} \right)=(\beta_{k 0}-\beta_{k' 0})+(\beta_{k 1}-\beta_{k' 1})x_{1}+\dots+(\beta_{xp}-\beta_{k'p})x_{p}.
$$


#ISLP #statistics #ML #classification #probability 