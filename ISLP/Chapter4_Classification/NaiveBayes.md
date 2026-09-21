#classification #ISLP #statistics #ML #probability #variance #mean 

Just like in [[LinearDiscriminantAnalysis|LDA]] and [[QuadraticDiscriminantAnalysis|QDA]], we use the [[TeoremaBayes|Bayes theorem]] to estimate a classifier.
To use the Bayes theorem, we need to find estimates for $\pi_{k}=P(Y=k)$ and $f_{k}(x)=P(X=x|Y=k)$ in order to estimate $p_{k}(x)=P(Y=k|X=x)$. Estimating $\pi_{k}$ is simple and straightforward, as we can approximate it as the proportion of each class, but estimating $f_{k}(x)$ is a lot harder. In both LDA and QDA, we assumed $f_{k}$ to be the density function of a multivariate [[DistribucionNormal|Gaussian]] distribution, which is a strong assumption that greatly simplifies the problem.

The *neive Bayes*  classifier uses a different approach for estimating $f_{k}(x)$. Instead of assuming that these functions belong to a family of distributions, we instead make one single assumption:
$$
	\text{Within the $k$-th class, the $p$ predictors are independent.}
$$
This means that for $k=1,\dots,K$, 
$$
	f_{k}(x)=f_{k 1}(x_{1})\times f_{k 2}(x_{2}) \times\dots \times f_{kp}(x_{p}),
$$
where $f_{kj}$ is the density function of the $j$-th predictor among observations in the $k$-th class. By making this assumption, we remove the need to worry about the relation between the predictors, because we are assuming that there is no relation.
So, plugin this approximation for $f_{k}$ into the Bayes theorem, we have that 
$$
	P(Y=k|X=x)= \frac{\pi_{k}\times f_{k 1}(x)\times\dots \times f_{kp}(x_{p})}{\sum_{l=1}^{K}\pi_{l}\times f_{l 1}(x_{1})\times\dots \times f_{lp}(x_{p})},
$$
for $k=1,\dots,K$.
In order to estimate our one-dimensional density function $f_{kj}$ using training data $x_{1j},\dots,x_{nj}$, we have a few options.