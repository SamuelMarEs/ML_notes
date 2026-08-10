Let $Y=[y_{1}, y_{2}, \dots, y_{n}]$ be the vector containing the response for all $n$ observations.
Let $x_{i}'=[1, x_{i 1}, \dots, x_{ip}]$ be the vector with the $p+1$ predictors for a specific $y_{i}$. Based on this, let 
$$
	X = \begin{bmatrix}
	1 & x_{11} & \dots & x_{1p} \\
	1 & \dot{} & \dots & x_{2p} \\
	\dot{} & \dot{} & \dots & \dot{} \\
	1 & x_{n 1}  & \dots & x_{np}
	\end{bmatrix}
$$
be the $n\times(p+1)$ matrix containing the predictors for all $n$ observations.
Let $\beta=[\beta_{0}, \beta_{1}, \dots, \beta_{p}]$ be the $p+1$ coefficients of the model.
Lastly, let $\epsilon=[\epsilon_{1},\dots,\epsilon_{n}]$ be the vector with the error terms.

We then have that 
$$
	Y=X\beta+\epsilon,
$$
or 
$$
	\begin{bmatrix}
	y_{1} \\
	y_{2} \\
	\dot{} \\
	y_{n}
	\end{bmatrix} = \begin{bmatrix}
	1 & x_{11} & \dots & x_{1p} \\
	1 & \dot{} & \dots & x_{2p} \\
	\dot{} & \dot{} & \dots & \dot{} \\
	1 & x_{n 1}  & \dots & x_{np}
	\end{bmatrix} \begin{bmatrix}
	\beta_{0} \\
	\beta_{1} \\
	\dot{} \\
	\beta_{p}
	\end{bmatrix} + \begin{bmatrix}
	\epsilon_{1} \\
	\epsilon_{2} \\
	\dot{} \\
	\epsilon_{n}
	\end{bmatrix}.
$$
We know that we can give an approximation for the coefficients $\hat{\beta}=[\hat{\beta_{0}}, \hat{\beta_{1}}, \dots, \hat{\beta_{p}}]$ such that 
$$
	Y \approx X \hat{\beta}.
$$
Assuming the errors $\epsilon_{i}$ to be independent and $\epsilon_{i}\sim\mathcal{N}(0, \sigma^{2})$ for each $i$, we can define the ***residual sum of squares*** as 
$$
	RSS = \sum_{i=1}^{n}(y_{i}-\hat{y_{i}})^{2}.
$$

So, we want to find a vector of coefficients $\hat{\beta}$ that minimizes the $RSS$. The solution to this problem is the ***normal equation*** 
$$
	\hat{\beta}=(X^{T}X)^{-1}X^{T}Y.
$$
##### Proof:
Let $\hat{\beta}$ be the OLS solution (minimizes the $RSS$) and let $\hat{\varepsilon}=Y-X\hat{\beta}$ be the resulting vector of residuals. $\hat{\varepsilon}$ is of the shape $n\times 1$ and our matrix $X$ is of the shape $n\times(p+1)$. $\hat{\varepsilon}$ and $X$ must be orthogonal, otherwise there would exist a different solution $\tilde{\beta}$ and $\tilde{\varepsilon}$. Thus, we have that 
$$
	\begin{align}
	 X^{T}\hat{\varepsilon}&=0 \\
	 X^{T}(Y-X\hat{\beta})&=0 \\
	 X^{T}Y-X^{T}X\hat{\beta}&=0 \\
	 X^{T}X\hat{\beta}&=X^{T}Y \\
	 \hat{\beta}&=(X^{T}X)^{-1}X^{T}Y. \quad \square
	\end{align}
$$
#### Corollary (Simple linear regression case)
Based on the normal equation, we can get the exact coefficients for a linear regression with only one predictor. That is, of the form 
$$
	Y \approx \beta_{0} + \beta_{1}X.
$$
For this, we have that 
$$
	\hat{\beta_{1}}=\frac{\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sum(x_{i}-\bar{x})^{2}},\quad \hat{\beta}_{0}=\bar{y}-\hat{\beta}_{1}\bar{x}.
$$
##### Proof:
Let $Y=[y_{1}, y_{2}, \dots, y_{n}]^{T}$, $X=\begin{bmatrix}1 & x_{1} \\  1 & x_{2} \\  \dot{} & \dot{} \\  1 & x_{n}\end{bmatrix}$, and thus $X^{T}=\begin{bmatrix}1 & 1 & \dots & 1 \\  x_{1} & x_{2} & \dots & x_{n}\end{bmatrix}$.
We also have $\hat{\beta}=[\hat{\beta}_{0}, \hat{\beta}_{1}]^{T}$.
First let us see that 
$$
	X^{T}X=\begin{bmatrix}
	n & \sum x_{i} \\
	\sum x_{i} & \sum x_{i}^{2}
	\end{bmatrix},
$$
and thus we have that 
$$
	(X^{T}X)^{-1}=\frac{1}{n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}}\begin{bmatrix}
	\sum x_{i}^{2} & -\sum x_{i} \\
	-\sum x_{i} & n
	\end{bmatrix}.
$$
Then, multiplying by $X^{T}$ again we have that 
$$
	(X^{T}X)^{-1}X^{T}=\frac{1}{n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}}\begin{bmatrix}
	\sum x_{i}^{2}-x_{1}\sum x_{i} & \dots & \sum x_{i}^{2}-x_{n}\sum x_{i} \\
	nx_{1}-\sum x_{i} & \dots & nx_{n}-\sum x_{i}
	\end{bmatrix}.
$$
Lastly, we multiply by $Y$ to obtain 
$$
	\begin{bmatrix}
	\hat{\beta_{0}} \\
	\hat{\beta}_{1}
	\end{bmatrix}=(X^{T}X)^{-1}X^{T}Y=\frac{1}{n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}}\begin{bmatrix}
	\left( \sum x_{i}^{2} \right)\left( \sum y_{i} \right)-\left( \sum x_{i} \right)\left( \sum x_{i}y_{i} \right) \\
	n\sum x_{i}y_{i}-\left( \sum x_{i} \right)\left( \sum y_{i} \right)
	\end{bmatrix},
$$
which translates to 
$$
	\hat{\beta}_{0}=\frac{\left( \sum x_{i}^{2} \right)\left( \sum y_{i} \right)-\left( \sum x_{i} \right)\left( \sum x_{i}y_{i} \right)}{n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}},
$$
and 
$$
	\hat{\beta}_{1}=\frac{n\sum x_{i}y_{i}-\left( \sum x_{i} \right)\left( \sum y_{i} \right)}{n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}}.
$$
Let us focus first on $\hat{\beta}_{1}$. Specifically on the expression $n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}$, which can be rewritten as 
$$
	\begin{align}
	&= n\sum x_{i}^{2}-\left( \sum x_{i} \right)^{2}-\left( \sum x_{i} \right)^{2} +\left( \sum x_{i} \right)^{2} \\
	&= n\left(\left( \sum x_{i}^{2} \right)-\frac{2}{n}\left( \sum x_{i} \right)^{2} +\frac{1}{n}\left( \sum x_{i} \right)^{2}\right) \\
	&= n\left(\left( \sum x_{i}^{2} \right)-2\bar{x}\sum x_{i} +\bar{x}\sum x_{i} \frac{n}{n}\right) \\
	&= n\left(\left( \sum x_{i}^{2} \right)-2\bar{x}\sum x_{i} +\sum\bar{x}^{2}\right) \\
	&= n\sum(x_{i}-\bar{x})^{2}.
	\end{align}
$$
We can perform similar algebra to the numerator $n\sum x_{i}y_{i}-\left( \sum x_{i} \right)\left( \sum y_{i} \right)$ as follows: 
$$
	\begin{align}
	&= n\left( \sum x_{i}y_{i} - \frac{1}{n}\left( \sum x_{i} \right)\left( \sum y_{i} \right)\right) \\
	&= n\left( \sum x_{i}y_{i} - \frac{1}{n}\left( \sum x_{i} \right)\left( \sum y_{i} \right) - \frac{1}{n}\left( \sum x_{i} \right)\left( \sum y_{i} \right) + \frac{1}{n}\left( \sum x_{i} \right)\left( \sum y_{i} \right) \frac{n}{n}\right) \\
	&= n\left( \sum x_{i}y_{i} - \bar{x}\left( \sum y_{i} \right) - \bar{y}\left( \sum x_{i} \right) + \sum\bar{x}\bar{y}\right) \\
	&= n\left( \sum x_{i}y_{i}-\bar{x}y_{i}-\bar{y}x_{i}+\bar{x}\bar{y} \right) \\
	&= n\sum(x_{i}-\bar{x})(y_{i}-\bar{y}).
	\end{align}
$$
Thus we have that 
$$
	\hat{\beta}_{1}=\frac{n\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{n\sum(x_{i}-\bar{x})^{2}}=\frac{\sum(x_{i}-\bar{x})(y_{i}-\bar{y})}{\sum(x_{i}-\bar{x})^{2}}.
$$

Now, the same but with $\hat{\beta}_{0}$. This time, is more convenient to look at the full fraction, instead of separately. We have 
$$
	\begin{align}
	\hat{\beta}_{0} &= \frac{1}{n} \frac{\left( \sum x_{i}^{2} \right)\left( \sum y_{i} \right)-\left( \sum x_{i} \right)\left( \sum x_{i}y_{i} \right)}{\sum(x_{i}-\bar{x})^{2}} \\
	&= \frac{1}{n}\left[ \frac{\left( \sum x_{i}^{2} \right)\left( \sum y_{i} \right)}{\sum(x_{i}-\bar{x})^{2}}- \frac{\left( \sum x_{i}y_{i} \right)\left( \sum x_{i} \right)}{\sum(x_{i}-\bar{x})^{2}}\right]  \\
	&= \frac{1}{n}\left[ \frac{\left( \sum x_{i}^{2} \right)\left( \sum y_{i} \right)}{\sum(x_{i}-\bar{x})^{2}}- \left( \hat{\beta}_{1} + \frac{\sum x_{i}\sum y_{i}}{n\sum (x_{i}-\bar{x})^{2}}\right)\left( \sum x_{i} \right)\right] \\
	&= \frac{1}{n}\left[ \frac{\sum y_{i}\left( n\sum x_{i}^{2} -\left( \sum x_{i} \right)^{2}\right)}{n\sum(x_{i}-\bar{x})^{2}}-\hat{\beta}_{1}\sum x_{i} \right] \\
	&= \bar{y}-\hat{\beta}_{1}\bar{x}.
	\end{align}
$$ Thus concluding the proof. $\square$




#statistics #theorem 