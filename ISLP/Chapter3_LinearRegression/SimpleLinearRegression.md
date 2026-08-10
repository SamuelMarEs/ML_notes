A straightforward approach for predicting a quantitative response $Y$ on the basis of a *single* variable $X$. We assume there to be a linear relation between the response and the predictor, which can be written as 
$$
	Y\approx \beta_{0}+\beta_{1}X.
$$
This method is called *regressing* $Y$ onto $X$. $\beta_{0}$ and $\beta_{1}$ represent the *intercept* and the *slope* terms of the linear model, and they're called the ***parameters*** or ***coefficients***.

### Estimating the coefficients
Let $\{ (x_{1},y_{1}),(x_{2},y_{2}),\dots,(x_{n},y_{n}) \}$ represent $n$ observation pairs for $x_{i}\in X$ and $y_{i}\in Y$. We want to estimate coefficients $\hat{\beta_{0}}$ and $\hat{\beta_{1}}$ such that $y_{i}\approx \hat{\beta_{0}}+\hat{\beta_{1}}x_{i}$ for $i=1,\dots,n$.
The most common approach to do this is minimizing the distance by the ***least squares*** method.
Let $\hat{y_{i}}$ be our prediction for $x_{i}$, and $y_{i}$ the true value at $x_{i}$. We define the ***residual sum of squares ($RSS$)*** as 
$$
	RSS = \sum_{i=1}^{n}(y_{i}-\hat{y_{i}})^{2}.
$$
We use what is called the [[OLS|ordinary least squares]] approach to choose $\hat{\beta_{0}}$ and $\hat{\beta_{1}}$ that minimize the $RSS$. In particular the coefficients are 
$$
	\hat{\beta_{1}}=\frac{\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sum(x_{i}-\bar{x})^{2}},\quad \hat{\beta}_{0}=\bar{y}-\hat{\beta}_{1}\bar{x},
$$
where $\bar{y}$ and $\bar{x}$ are our [[MuestrasAleatorias|sample means]] for the response and the predictor.

### Accuracy of the coefficients
##### Standard error
Given our sample mean for $Y$, $\hat{\mu}=\bar{y}=\frac{1}{n}\sum y_{i}$, we can define the ***standard error*** to know the accuracy of the sample mean as an approximation of the true mean: 
$$
	Var(\hat{\mu})=SE(\hat{\mu})^{2}=\frac{\sigma^{2}}{n},
$$
where $\sigma$ is the [[Varianza_DesviacionEstandar|standard deviation]] of each $y_{i}$ from $Y$. We can then use the standard error to compute how close $\hat{\beta_{0}}$ and $\hat{\beta_{1}}$ are to the true values $\beta_{0}$ and $\beta_{1}$, using the formulas 
$$
	SE(\hat{\beta_{0}})^{2}=\sigma^{2}\left[ \frac{1}{n}+\frac{\bar{x}^{2}}{\sum(x_{i}-\bar{x})^{2}} \right],\quad SE(\hat{\beta_{1}})^{2}=\frac{\sigma^{2}}{\sum(x_{i}-\bar{x})^{2}}.
$$

Strictly speaking, $\sigma$ is unknown, but it can be estimated using what is called the ***residual standard error***, given by 
$$
	RSE=\sqrt{ \frac{RSS}{n-2} }.
$$
Thus, we can use the $RSE$ to give an estimate $\hat{SE}$.
##### Confidence intervals
Using the standard errors (or their approximations), we can compute the ***confidence intervals***. A $95\%$ confidence interval is defined as the range of values that contains the true value of the parameter with a $95\%$ probability. For linear regression, the $95\%$ confidence interval for the predictors is of the form 
$$
	\hat{\beta_{1}}\pm 2SE(\hat{\beta_{1}}), \quad \hat{\beta_{0}}\pm 2SE(\hat{\beta_{0}}).
$$
##### Hypothesis tests
We can also use the standard errors to perform ***hypothesis tests*** on the coefficients. The most common form of test if comparing the *null hypothesis* to the *alternative hypothesis*:
$$
	\begin{align}
	H_{0}:\text{there's no relation between $X$ and $Y$. } ( \beta_{1} = 0)\\
	H_{a}:\text{there's some relation between $X$ and $Y$. } ( \beta_{1} \neq 0)
	\end{align}
$$
To test the null hypothesis, we check that our estimate $\hat{\beta_{1}}$ is sufficiently far from $0$ such that $\beta_{1}$ can't be $0$. This depends on our $SE(\hat{\beta_{1}})$. The larger it is, the larger $\lvert \hat{\beta_{1}} \rvert$ must be in order to reject the null  hypothesis.
In practice, what we do is compute a ***t-statistic***, defined as 
$$
	t=\frac{\hat{\beta_{1}}-\mu}{SE(\hat{\beta_{1}})}.
$$
(In this particular case, we have $\mu=0$).
Then we define the ***p-value*** as the probability of observing any number equal to $\lvert t \rvert$ or larger in absolute value. A small p-value indicates that there's some relation between the prediction and the response, which allows us to *reject* the null hypothesis. Typical p-values considered small are 5% or 1%.

### Model Accuracy
After rejecting the null hypothesis, we want to know the extent to which the model fits the data. Due to the irreducible error, we will never be able to predict $Y$ from $X$ perfectly, but we can get close.
The $RSE$ (residual standard error) can be interpreted as the average amount the response will deviate from the true regression line. The smaller it is, the better. 

An alternative measure of model fit is the ***$R^2$-statistic***, defined as 
$$
	R^{2}=\frac{TSS-RSS}{TSS}=1-\frac{RSS}{TSS},
$$
where $TSS$ is the ***Total Sum of Squares***: 
$$
	TSS=\sum_{i=1}^{n}(y_{i}-\bar{y})^{2},
$$
where $\bar{y}$ is the sample mean. 
If $R^{2}$ is close to 1, then a large proportion of the variability in the response is explained by the regression. If it's near 0, then the regression does not explain much of the variability.

Another measure of linear relationship between $X$ and $Y$ si the [[Covarianza_Correlacion|correlation]]:
$$
	Cor(X,Y)=\frac{\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sqrt{ \sum(x_{i}-\bar{x})^{2} }\sqrt{ \sum(y_{i}-\bar{y})^{2} }}.
$$


#statistics #ISLP #mean #error #variance #probability