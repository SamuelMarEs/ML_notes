#ISLP #statistics #probability #classification #mean #variance #ML
[[LinearDiscriminantAnalysis|LDA]] assumes that the observations within each class are drawn from a multivariate Gaussian distribution, with a class specific mean vector and a covariance matrix that is common to all $K$ classes.
Once again, we assume that the observations from each class are drawn from a [[DistribucionNormal|Gaussian distribution]], however, unlike LDA, QDA (Quadratic Discriminant Analysis)  assumes that each class has its own [[Covarianza_Correlacion|covariance]] matrix. In other words, an observation from the $k$-th class is assumed to be of the form $X\sim\mathcal{N}(\mu_{k},\Sigma_{k})$, where $\Sigma_{k}$ is a covariance matrix for the $k$-th class.
Under this assumption, we assign $X=x$ to the class for which 
$$
	\begin{align}
	\delta_{k}(x)&=-\frac{1}{2}(x-\mu_{k})^{T}\Sigma_{k}^{-1}(x-\mu_{k})- \frac{1}{2}\ln|\Sigma_{k}|+\ln \pi_{k} \\
	&=\frac{1}{2}x^{T}\Sigma_{k}^{-1}x+x^{T}\Sigma_{k}^{-1}\mu_{k}- \frac{1}{2}\mu_{k}^{T}\Sigma_{k}^{-1}\mu_{k}- \frac{1}{2}\ln|\Sigma_{k}|+\ln \pi_{k}
	\end{align}
$$
is largest. This is once again obtained using the [[TeoremaBayes|Bayes theorem]] with the idea of approximating the [[ClassificationSetting|Bayes classifier]].
Now, we have to obtain estimates for $\Sigma_{k},\mu_{k}$ and $\pi_{k}$ to plug into our discriminant function, and assign an observation $X=x$ to the class for which this quantity is largest. In this case, the quantity $x$ appears as a quadratic function, which explains why QDA gets its name.

Why should we choose QDA over LDA, or vice versa? The answer lies in the [[AssessingModelAccuracy|bias-variance tradeoff]]. When there are $p$ predictors, estimating a covariance matrix requires estimating $\frac{p(p+1)}{2}$ parameters. Thus, QDA has to estimate a total of $\frac{Kp(p+1)}{2}$ parameters, which is a lot, while LDA only has to estimate $Kp$ linear coefficients.
Also, LDA is a much less flexible classifier than QDA, and thus it has lower variance. In the case for which the assumption that the $K$ classes share a common covariance matrix is badly off, then LDA can suffer from high bias.
In general, LDA is recommended for cases in which the training observations are few, while QDA is recommended when the training set is large, or if the assumption of a common covariance matrix seems ilogical.
