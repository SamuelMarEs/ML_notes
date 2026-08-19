### for p=1
First let's assume that $p=1$, that is, we have only one predictor. We will obtain an estimate for $f_{k}(x)$ that we can use to estimate $p_{k}(x)$. Then we will classify an observation to the class for which $p_{k}(x)$ is greatest. 
First, we assume that $f_{k}(x)$ is [[DistribucionNormal|normal or Gaussian]]. In the one-dimensional case, the normal density takes the form 
$$
	f_{k}(x)=\frac{1}{\sqrt{ 2\pi }\sigma_{k}}\exp\left(- \frac{(x-\mu_{k})^{2}}{2\sigma_{k}^{2}} \right),
$$
where $\mu_{k}$ and $\sigma_{k}^{2}$ are the [[ValorEsperado|mean]] and [[Varianza_DesviacionEstandar|variance]] parameters for the $k$-th class. 
For now, let's assume that $\sigma_{1}^{2},\dots,\sigma_{K}^{2}$, that is, all $K$ classes share a variance, which we'll denote $\sigma^{2}$.
We can plug this $f_{k}(x)$ into our equation for [[GenerativeModels_Intro|probability]], which gives us 
$$
	p_{k}(x)=\frac{\pi_{k} \frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right) }{\sum_{l=1}^{K}\pi_{l}\frac{1}{\sqrt{ 2\pi }\sigma}\exp\left(-\frac{1}{2\sigma^{2}} (x-\mu_{k})^{2}\right) }.
$$



#ISLP #statistics #classification #probability 
