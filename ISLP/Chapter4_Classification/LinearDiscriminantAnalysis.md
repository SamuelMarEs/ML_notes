### for $p=1$
First let's assume that $p=1$, that is, we have only one predictor. We will obtain an estimate for $f_{k}(x)$ that we can use to estimate $p_{k}(x)$. Then we will classify an observation to the class for which $p_{k}(x)$ is greatest. 
First, we assume that $f_{k}(x)$ is [[DistribucionNormal|normal or Gaussian]]. In the one-dimensional case, the normal density takes the form 
$$
	f_{k}(x)=\frac{1}{\sqrt{ 2\pi }\sigma_{k}}\exp\left(- \frac{(x-\mu_{k})^{2}}{2\sigma_{k}^{2}} \right),
$$
where $\mu_{k}$ and $\sigma_{k}^{2}$ are the [[ValorEsperado|mean]] and [[Varianza_DesviacionEstandar|variance]] parameters for the $k$-th class. 
For now, let's assume that $\sigma_{1}^{2}=\dots=\sigma_{K}^{2}$, that is, all $K$ classes share a variance, which we'll denote $\sigma^{2}$.
We can plug this $f_{k}(x)$ into our equation for [[GenerativeModels_Intro|probability]], which gives us 
$$
	p_{k}(x)=\frac{\pi_{k} \frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right) }{\sum_{l=1}^{K}\pi_{l}\frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right) }.
$$
Remember that $\pi_{k}$ denotes the probability of any observation to belong to the $k$-th class, i.e. $\pi_{k}=P(Y=k)$.
We want to assign our observation $X=x$ to the class for which $p_{k}(x)$ is largest. If we take the $\ln$ and rearrange the terms, we can show that this is equivalent to assigning the observation to the class for which 
$$
	\delta_{k}(x)=x \frac{\mu_{k}}{\sigma^{2}}-\frac{\mu_{k}^{2}}{2\sigma^{2}}+\ln(\pi_{k})
$$
is largest.
###### Proof:
Let $p_{k}(x)$ be as it is defined above. By taking the $\ln$ on both sides, we have that 
$$
	\ln (p_{k}(x))=\ln(\pi_{k})+\ln\left( \frac{1}{\sqrt{ 2\pi }\sigma} \right)+\frac{(x-\mu_{k})^{2}}{-2\sigma^{2}}-\ln\left(\sum_{l=1}^{K}\pi_{l}\frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right)\right).
$$
The reason we can do this is because $\ln$ is continuos and strictly increasing for any positive number, and thus assigning our observation $X=x$ to the class for which $p_{k}(x)$ is largest is the same as assigning it to the class for which $\ln(p_{}(x))$ is largest.
Notice that 
$$
	\sum_{l=1}^{K}\pi_{l}\frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right)=P(X=x),
$$
and thus we have that 
$$
	\begin{align}
	\ln (p_{k}(x))&=\ln(\pi_{k})+\ln\left( \frac{1}{\sqrt{ 2\pi }\sigma} \right)+\frac{(x-\mu_{k})^{2}}{-2\sigma^{2}}-\ln(P(x)) \\
	&=\ln(\pi_{k})+\ln\left( \frac{1}{\sqrt{ 2\pi }\sigma} \right)-\frac{x^{2}}{2\sigma^{2}}+\frac{x\mu_{k}}{\sigma^{2}}-\frac{\mu_{k}^{2}}{2\sigma^{2}}-\ln(P(x)).
	\end{align}
$$
Notice that, if we hold $x$ still (which we do when comparing $p_{k}(x)$ for two different classes), we have that the following terms don't depend on the class, that is, we can "forget" about them: 
$$
	\ln\left( \frac{1}{\sqrt{ 2\pi }\sigma} \right),\quad \frac{x^{2}}{2\sigma^{2}},\quad\ln(P(x)).
$$
Thus, we are left with the expression we were looking for:
$$
	\delta_{k}(x)=\frac{x\mu_{k}}{\sigma^{2}}-\frac{\mu_{k}^{2}}{2\sigma^{2}}+\ln(\pi_{k}).\quad\square
$$


For example, if $K=2$ and $\pi_{1}=\pi_{2}$, then we are assigning an observation to class 1 if $2x(\mu_{1}-\mu_{2})<\mu_{1}^{2}-\mu_{2}^{2}$, and to class 2 otherwise (trivial).
The *Bayes decision boundary* is the point for which $\delta_{1}(x)=\delta_{2}(x)$, which is 
$$
	x = \frac{\mu_{1}+\mu_{2}}{2}.
$$
The *linear discriminant analysis* (LDA) method approximates the [[ClassificationSetting|Bayes classifier]] by plugging estimates for $\pi_{k},\mu_{k}$ and $\sigma^{2}$ into $\delta_{k}(x)$. 
In particular, we use the following estimates: 
$$
	\hat{\mu}_{k}=\frac{1}{n_{k}}\sum_{i:y_{i}=k}x_{i},\quad \hat{\sigma}^{2}=\frac{1}{n-K}\sum_{k=1}^{K}\sum_{i:y_{i}=k}(x_{i}-\hat{\mu}_{k})^{2},
$$
where $n$ is the total number of training observations, and $n_{k}$ is the number of training observations in the $k$-th class. $\mu_{k}$ is basically the average of all the training observations from the $k$-th class, and $\sigma^{2}$ can be seen as a weighted average of the variances for each of the $K$ classes.
In order to estimate $\pi_{k}$, we use the proportion of the training observations that belong to the $k$-th class. That is: 
$$
	\hat{\pi}_{k}=\frac{n_{k}}{n}.
$$
We use this estimates in order to try and give the best estimate 
$$
	\hat{\delta}_{k}(x)=\frac{x\hat{\mu}_{k}}{\hat{\sigma}^{2}}-\frac{\hat{\mu}_{k}^{2}}{2\hat{\sigma}^{2}}+\ln(\hat{\pi}_{k}).
$$
The name of *linear* discriminant analysis stems from the fact that the ***discriminant functions*** $\hat{\delta}_{k}(x)$ are linear functions of $x$.

### for $p>1$
We now want to extend the **LDA** to the case of multiple predictors. To do this we'll assume that $X=(X_{1},\dots,X_{p})$ is drawn from a *multi-variate Gaussian* (or multivariate normal) distribution, with a class-specific mean vector and a common [[Covarianza_Correlacion|covariance]] matrix.
To indicate that our $p$-dimensional random variable $X$ has a multivariate Gaussian distribution, we write $X\sim\mathcal{N}(\mu,\Sigma)$. Here $E(X)=\mu$ is the mean of $X$, and $\text{Cov}(X)=\Sigma$ is the $p\times p$ covariance matrix of $X$. Formally the multivariate Gaussian density is defined as 
$$
	f(x)=\frac{1}{(2\pi)^{p / 2}|\Sigma|^{1 / 2}}\exp\left( -\frac{1}{2}(x-\mu)^{T}\Sigma ^{-1}(x-\mu) \right).
$$
So, now our linear discriminant analysis will assume that the observations in the $k$-th class are drawn from a multivariate Gaussian $\mathcal{N}(\mu_{k},\Sigma)$. 
By performing some algebra on $p_{k}(x)$ in a similar way as with the $p=1$ case, can reach our discriminant function 
$$
	\delta_{k}(x)=x^{T}\Sigma ^{-1}\mu_{k}-\frac{1}{2}\mu_{k}T\Sigma ^{-1}\mu_{k}+\ln(\pi_{k}),
$$
just that in this case we are treating with a vector/matrix version of the discriminant.
The Bayes decision boundaries is the set for which $\delta_{k}(x)=\delta_{\ell}(x)$, i.e. 
$$
	x^{T}\Sigma ^{-1}\mu_{k}-\frac{1}{2}u_{k}^{T}\Sigma ^{-1}\mu_{k}=x^{T}\Sigma ^{-1}\mu_{\ell}-\frac{1}{2}u_{\ell}^{T}\Sigma ^{-1}\mu_{\ell},
$$
assuming that $\pi_{k}=\pi_{\ell}$. There will be as many decision boundaries as there are pairs of classes.


#ISLP #statistics #classification #probability 
