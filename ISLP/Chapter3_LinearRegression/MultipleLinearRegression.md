In practice, there's usually more than just one predictor. Instead of using multiple regressions for each predictor, we accommodate the simple linear regression model to fit multiple predictors. We do this by giving each predictor a different slope: 
$$
	Y\approx \beta_{0}+\beta_{1}X_{1}+\beta_{2}X_{2}+\dots+\beta_{p}X_{p},
$$
where $X_{j}$ is the $j$-th predictor and $\beta_{j}$ the association between that variable and the response. 
$\beta_{j}$ is interpreted as the average effect on $Y$ of a one unit increase in $X_{j}$ holding all the other predictors fixed.

### Estimating the coefficients
Just as with [[SimpleLinearRegression|simple linear regression]] we can give estimates $\hat{\beta_{0}},\hat{\beta_{1}},\dots,\hat{\beta_{p}}$ to predict a response $\hat{y_{i}}$. Once again, we want to choose the predictors that minimize the *residual sum of squares* 
$$
	RSS=\sum_{i=1}^{n}(y_{i}-\hat{y_{i}})^{2}=\sum_{i=1}^{n}(y_{i}-\hat{\beta_{0}}-\hat{\beta_{1}}x_{i 1}-\dots-\hat{\beta_{p}}x_{ip})^{2}.
$$
This is again done by the [[OLS|ordinary least squares method]], which gives as a result what is known as the ***normal equation*** for linear regression: 
$$
	\hat{\beta}=(X^{T}X)^{-1}X^{T}Y,
$$
where $\hat{\beta}=[\hat{\beta_{0}},\hat{\beta_{1}},\dots,\hat{\beta_{p}}]$, $Y=[y_{1}, y_{2}, \dots, y_{n}]$ is the vector with the responses, and $X$ is a matrix containing the values of all $p$ predictors for the $n$ observations. 

Even if simple linear regression shows a relationship between two variables, multiple linear regression might show that there's actually no relationship in reality, when considering other variables.

### Important questions
##### 1. Is there a relation between the response and the predictors?
Now, our *null hypothesis* and *alternative hypothesis* will look like this: 
$$
	\begin{align}
	H_{0}&:\beta_{1}=\beta_{2}=\dots=\beta_{p}=0\quad(\text{no predictor is related to the response}) \\
	H_{a}&: \exists\quad \beta_{j} \quad\text{such that}\quad \beta_{j}\neq 0\quad(\text{at least one $\beta_j$ is non-zero}).
	\end{align}
$$
This hypothesis test is computed using the ***$F$-statistic*** 
$$
	F=\frac{(TSS-RSS)/p}{RSS/(n-p-1)},
$$
where $p$ is the number of predictors and $n$ the number of observations. If $p>n$, then the $F$-statistic can't be used.
If $F$ is close to 1, then we expect the null hypothesis to be true. Otherwise, we expect $F$ to be greater than 1. Now arises the question, how far away from 1 must $F$ be in order to reject the null-hypothesis?. In order to answer this question, we can compute a p-value associated with the $F$-statistic, and based on it decide whether to reject or not $H_{0}$.
We can also compute an $F$-statistic taking into account only a subset $q$ of predictors: 
$$
	F=\frac{(TSS-RSS)/q}{RSS/(n-p-1)}.
$$
It's important to note that the $t$-statistic and p-value of a single predictor is exactly equivalent to the $F$-statistic when removing said predictor. More precisely, the square of the $t$-statistic is the corresponding $F$-statistic.
##### 2. Deciding on important variables
After rejecting $H_{0}$ and concluding that some predictors are related to the response, we ask, which ones?
One option is to look at the individual p-values, but for a large number of predictors this doesn't work.
We could also check all $2^{p}$ models for each subset of predictors, but most of the times in practice it isn't possible. 
There's three classical approaches for *variable selection*:
1. Forward selection: starting with a null model, and the we fit $p$ simple linear regressions, and add the variable with the lowest $RSS$ to the model. We repeat until some stopping condition is met.
2. Backward selection: starting with all variables in the model, we remove the one with larger p-value, and repeat, until some stopping rule is satisfied. For example, we could stop when all remaining p-values are below a certain range.
3. Mixed selection: combination of the previous two. We start with forward selection, but when the p-value of a variable rises above a certain limit, we remove that variable. We stop when all variables in the model have low p-value, and those outside of the model have high p-value if added.
##### 3. Model fit
The two most common numerical measures of model fit are the $RSE$ and the $R^{2}$-statistic. They are computed and interpreted in the same manner as in [[SimpleLinearRegression|simple regression]].
The $R^{2}$ will always increase when more variables are added into the model, even if they are not statistically significant. However, a small increase might provide evidence that the variable isn't important, while larger increases might prove the opposite, and that the variable has a strong relation with the response.
In general, we compute the $RSE$ as 
$$
	RSE=\sqrt{ \frac{RSS}{n-p-1} }.
$$
Plotting the data might also help to understand model fit.
##### 4. Predictions
Once we have our model, we can predict $Y$ on the basis of a set of predictors $X_{1},X_{2},\dots,X_{p}$. However, there are three sorts of uncertainty associated with the prediction:
1. The estimates for our coefficients $\hat{\beta}$ give us the *least squares plane*, but there's always some reducible error. Thus, we can compute *confidence intervals* to determine how close $\hat{Y}$ will be to $f(x)$.
2. In practice, assuming the true function $f(x)$ to be linear is almost always just an approximation, so there's another source of potentially reducible error called ***model bias***. A linear model gives the best linear approximation to the true surface.
3. Even if we knew $f(x)$, there's the random error $\epsilon$. So, we can compute ***prediction intervals***. They are always wider than confidence intervals because they take into account both reducible and irreducible error.
*Confidence intervals* quantify the uncertainty surrounding the average. If we say that the 95% confidence interval is $[a,b]$, that means that 95% of intervals of that form will contain the true value of $f(x)$.
*Prediction intervals* also quantify uncertainty, but surrounding a specific sample instead of the average. Again, given the 95% prediction interval $[c,d]$, we interpret that 95% of such intervals will contain the true value of $Y=f(x)+\epsilon$.
One important property is that $[a,b]\subset[c,d]$.


#statistics #ISLP #error #ML #regression 