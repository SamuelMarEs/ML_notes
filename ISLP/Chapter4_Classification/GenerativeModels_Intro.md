In [[LogisticRegression|logistic regression]] we model the conditional distribution $P(Y=k|X=x)$ of the response $Y$ given the predictor(s) $X$. We now consider another approach to estimate this probabilities. 
In this new approach we model the distribution of the predictors $X$ separately from the response $Y$. Then we use the [[TeoremaBayes|Bayes' theorem]] to switch this into estimates for $P(Y=k|X=x)$.

Some reasons why we do this instead of just using logistic regression are:
- When there's substantial separation between classes, the parameter estimates for logistic regression are unstable. 
- If the distribution of the predictors $X$ is approximately normal in each of the classes and the sample size is small, then some approaches may be more accurate than logistic regression.
- The methods in this section can be naturally extended to more than two response classes.

Suppose that we wish to classify an observation into one of $K$ classes with $K\geq 2$. Let $\pi_{k}$ represent the overall or *prior* probability that a randomly chosen observation comes from the $k$-th. Let $f_{k}(X)\equiv P(X|Y=k)$ denote the *density function* of $X$ for an observation that comes from the $k$-th class. In other words, $f_{k}(x)$ is relatively large if there is a high probability that an observation in the $k$-th class has $X\approx x$. Then [[TeoremaBayes|Bayes' theorem]] states that 
$$
	P(Y=k|X=x)=\frac{\pi_{k}f_{k}(x)}{\sum_{l=1}^{K}\pi_{l}f_{l}(x)}.
$$
We can use the abreviation $p_{k}(x)=P(Y=k|X=x)$; this is the *posterior* probability that an observation $X=x$ belongs to the $k$-th class. This way, instead of triying to compute $p_{k}(x)$ we can simply plug in estimates of $\pi_{k}$ and $f_{k}(x)$ into the Bayes' theorem. However, estimating $f_{k}(x)$ is often more challenging.

The next are three classifiers that use different estimates of $f_{k}(x)$ to approximate the Bayes classifier: [[LinearDiscriminantAnalysis|linear discriminant analysis]], [[QuadraticDiscriminantAnalysis|quadratic discriminant analysis]], and [[NaiveBayes|naive Bayes]].

#ISLP #statistics #probability #ML #classification 