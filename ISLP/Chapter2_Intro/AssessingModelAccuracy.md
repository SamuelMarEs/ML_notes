It's essential to determine which method is the best for any given data set. Selecting the best approach can be very challenging.

### Quality of fit
The performance of a specific method can be evaluated by how well the predictions match the data.
The main way of doing this is with the *mean squared error (MSE)* given by 
$$
	MSE=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{f}(x_i)).
$$
Given our *training* observations $\{(x_{1},y_{1}),(x_{2},y_{2}),\dots(x_{n},y_{n})\}$, we obtain our estimate $\hat{f}$, allowing us to compute $\hat{f}(x_{i})$, and if it approximates $y_{i}$, then the *training MSE* will be small.
However, we also have to take into account the *test MSE*, which measures whether $\hat{f}(x_{0})$ approximates $y_{0}$, where $(x_{0},y_{0})$ is an observation not used in the training of the model.
More [[Intro_ISLP|flexibility]] in our model results in less training MSE, bu the same doesn't always apply to the test MSE.

### Bias-Variance tradeoff
The [[ValorEsperado|expected]] test MSE for a given value $x_{0}$ can always be decomposed into the sum of:
- the [[Varianza_DesviacionEstandar|variance]] of $\hat{f}(x_0)$,
- the squared *bias* of $\hat{f}(x_0)$,
- and the variance of the error terms $\epsilon$,
which is written as 
$$
	E[(y_{0}-\hat{f}(x_{0}))^{2}]=Var(\hat{f}(x_{0}))+[Bias(\hat{f}(x_{0}))]^{2}+Var(\epsilon).
$$
Here, $Var(\epsilon)$ is our *irreducible error*. Thus, we can see that, in order to minimize the MSE we must minimize the variance and the bias of $\hat{f}(x_{0})$.
- Variance: can be interpreted as the amount by which $\hat{f}$  would change if estimated using different training data. In general, more flexible methods have larger variance, as they tend to to stick more to the training data.
- Bias: Error introduced by approximating a real life problem, which may be extremely complicated, using a much simpler model. For example, linear regression will result in some bias in the estimate of $f$, as it is unlikely that a real life problem follows a linear relationship. Generally more flexible methods reduce the bias.
  Mathematically, the bias is defined as 
  $$
	Bias(\hat{f}(x_{0}))=E[\hat{f}(x_{0})]-f(x_{0}).
  $$
So, we can see that a flexible method might reduce the bias, but increase the variance. Thus, the ideal would be to find the sweet spot between bias and variance, resulting in the bias-variance tradeoff. 



#ISLP #statistics #error #mean #variance #ML