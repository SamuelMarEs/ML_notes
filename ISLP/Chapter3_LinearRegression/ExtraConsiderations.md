The [[SimpleLinearRegression|linear regression]] model is based on two very important assumptions; ***additivity*** and ***linearity*** in the relation between the predictor and the response.
- The additivity assumption is that the association between $X_i$ and $Y$ does not depend on other predictors.
- The linearity assumption is that the change of $Y$ with respect to $X_i$ is constant.
### Extensions
#### 1. Removing the additive assumption
We introduce the concept of ***interaction effect***, which refers to how changes in one predictor might influence the coefficient of another, which the linear models don't take into account. Given a model of the form 
$$
	Y=\beta_{0}+\beta_{1}X_{1}+\beta_{2}X_{2}+\epsilon,
$$
we can introduce a third predictor, called an ***interaction term***, constructed as the product of $X_{1}$, and $X_{2}$: 
$$
	\begin{align}
	Y&=\beta_{0}+\beta_{1}X_{1}+\beta_{2}X_{2}+\beta_{3}X_{1}X_{2}+\epsilon \\
	&= \beta_{0}+\tilde{\beta_{1}}X_{1}+\beta_{2}X_{2}+\epsilon,
	\end{align}
$$
where $\tilde{\beta_{1}}=\beta_{1}+\beta_{3}X_{2}$. Thus we can see how changes in $X_{2}$ will affect $X_{1}$, and viceversa.
**Hierarchical principle:** if some predictors $X_{i}$ and $X_{j}$ show a strong or importan interaction, hen both should be included in the model, even if their coefficients show high p-values individually. This applies both for qualitative and quantitative predictors.
#### 2. Non-linear Relationships
We can extend the linear model to account for a non-linear relationship between the predictor and the response by using what's called ***polynomial regression***.
For example, let's assume we believe there to be a quadratic relation between a response $Y$ and the predictor $X$. In this case, we could a model of the form 
$$
	Y=\beta_{0}+\beta_{1}X+\beta_{2}X^{2}+\epsilon.
$$
This is still a linear model, in particular it is a [[MultipleLinearRegression|multiple linear regression]] with $X_{1}=X$ and $X_{2}=X^{2}$.
Depending on the problem, we might also include $X_{3}=X^{3}$, $X_{4}=X^{4}$, and so forth.

### Potential problems
The following are some problems that might appear when working with a linear model, described briefly:
1. Non-linearity of the data: one tool for identifying non-linearity are Residual Plots, which, ideally, shouldn't show a pattern. If they do, it might be an indicator of non-linearity, indicating that we should probably choose another type of model.
2. [[Covarianza_Correlacion|Correlation]] of error terms: another assumption of the linear regression model is hat the error terms $\epsilon_i$ are uncorrelated. If there is in fact a correlation in the error terms, this might lead to inaccurate p-values, erroneous conclusions, and wrong coefficients and hypothesis tests.
3. Non-constant [[Varianza_DesviacionEstandar|variance]] of error terms: for a linear model we assumed that all the errors shared $Var(\epsilon_i)=\sigma^{2}$. Both confidence intervals and hypothesis tests rely heavily on this assumption. Non-constan variance is called *heteroscedasticity*, and can be identified by a "funnel shape" in the residual plot. The opposite is called *homoscedasticity*.
![[Heteroscedasticity.png]]
4. Outliers: an ***outlier*** is a point for which $y_i$ is very far from the predicted value by the model. They can heavily affect the $RSE$, and thus also the p-value, confidence intervals, and other measures.
   One possibility is that an outlier is a result of an error in data collection, in which case one simple solution is to remove it from the data. However, an outlier might also indicate a deficiency in the model.
5. High leverage points: a ***high leverage point*** is one with unusual values for $x_i$. The predictor value is outside of the normal range of the observations. In multiple linear regression, we might have an observation with normal ranges individually, bu unusual in terms of the full set. To quantify an observations leverage, we use the ***leverage statistic***, which for simple linear regression is computed as follows: 
   $$
   	h_{i}=\frac{1}{n}+\frac{(x_{i}-\bar{x})^{2}}{\sum_{k}(x_{k}-\bar{x})^{2}}.
   $$
6. Collinearity: ***collinearity*** refers to the situation where two ro more predictors are closely related. This can make it difficult to separate the individual effect of each predictor on the response. There's also ***multicollinearity***, which is when more than two predictors show a strong relation, but there's no strong relation when looking at them in pairs.
   Some solutions to this problem include dropping one of the variables, or combining them into a single predictor.

#statistics #ISLP #variance #error