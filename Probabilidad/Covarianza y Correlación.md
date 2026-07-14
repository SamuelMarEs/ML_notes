# Covarianza

La covarianza es una métrica de [[Probabilidad Conjunta]].
La covarianza mide cómo varían de forma conjunta dos [[Variable aleatoria]]s:

$$ \text{Cov}(X, Y) = E\!\left[(X - \mu_X)(Y - \mu_Y)\right]. $$

### Propiedades

**1.**

$$ 
\begin{align*}
\text{Cov}(X,Y) &= E(XY - \mu_Y X - \mu_X Y + \mu_X \mu_Y) \\
&= E(XY) - \mu_Y E(X) - \mu_X E(Y) + \mu_X \mu_Y.
\end{align*}
$$

Recordemos que $\mu_X = E(X)$ y $\mu_Y = E(Y)$, entonces:

$$ = E(XY) - E(X)E(Y) - E(X)E(Y) + E(X)E(Y) = E(XY) - E(X)E(Y). $$

**1.5.** Si $X$ y $Y$ son independientes, $\text{Cov}(X,Y) = 0$ (pues $E(XY) = E(X)E(Y)$). El reverso no necesariamente es cierto.

**2.** $\text{Cov}(X, X) = \text{Var}(X)$.

**3.** $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2\,\text{Cov}(X,Y)$.

# Correlación

La correlación de $X$ y $Y$ se define como:

$$ \text{Corr}(X,Y) = \frac{\text{Cov}(X,Y)}{\text{SD}(X)\,\text{SD}(Y)} = \frac{\sigma_{XY}}{\sigma_X\,\sigma_Y}. $$

Una propiedad es que $\text{Corr}(aX+b,\, cY+d) = \text{Corr}(X,Y)$.