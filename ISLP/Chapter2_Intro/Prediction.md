Let $X=\{X_{1},X_{2},\dots,X_{p}\}$ be the set of $p$ predictors, and $Y$ be our response.
A lot of times we know $X$ but we do not know $Y$. Since we know that the error terms $\epsilon$ average zero, we can predict $Y$ using 
$$
	\hat{Y}=\hat{f}(X),
$$
where $\hat{f}$ is our best estimate for the true $f$, and $\hat{Y}$ the resulting prediction for $Y$.

The accuracy of $\hat{Y}$ as a prediction for $Y$ depends on two quantities:
1. Reducible error: error dependent on $X$ that we can minimize by improving the accuracy of $\hat{f}$ to predict $f$.
2. Irreducible error: no matter how well we estimate $f$, we can't reduce the error term $\epsilon$, as it's independent from $X$.

Consider a given estimate $\hat{f}$ and a set of predictors $X$, which yields the prediction $\hat{Y}=\hat{f}(X)$. Assume both $\hat{f}$ and $X$ fixed, so that the only variability comes from $\epsilon$. Then we can show that 
$$
	E[(Y-\hat{Y})^{2}]=E[(f(X)+\epsilon-\hat{f}(X))^{2}]=[f(X)-\hat{f}(X)]^{2}+Var(\epsilon).
$$
Since we assume $\hat{f}$ and $X$ fixed (constant), and $\epsilon$ is our random variable with mean zero ($E(\epsilon)=0$), we can use the properties of the [[ValorEsperado|expected value]], and the [[Varianza_DesviacionEstandar|variance]] to easily show that the equation above holds true. The term $Var(\epsilon)$ is called the irreducible error.

#ISLP #statistics #mean #variance #error #ML