Dada una secuencia de [[Variable aleatoria]]s independientes $X_1, X_2, \ldots, X_n$ tal que comparten el mismo [[Valor Esperado]] $E(X_i) = \mu$, y la misma [[Varianza y Desviación Estándar]] $\text{Var}(X_i) = \sigma^2$. Entonces la media de las muestras converge a $\mu$ cuando $n \to \infty$:

$$ \bar{X}_n = \frac{1}{n}\sum_{i=1}^n X_i, $$
$$\lim_{n\to\infty}\bar{X}_{n}=\mu.$$

Formalmente esto implica que $P(|\bar{X}_n - \mu| > \varepsilon) \to 0$ cuando $n \to \infty$.

#### **Demostración:** 
Dado que las $X_i$ son independientes, entonces:

$$ E(\bar{X}_n) = \frac{1}{n}\sum_{i=1}^n E(X_i) = \frac{n\mu}{n} = \mu. $$

Además:

$$ \text{Var}(\bar{X}_n) = \frac{1}{n^2}\sum_{i=1}^n \text{Var}(X_i) = \frac{n\sigma^2}{n^2} = \frac{\sigma^2}{n}. $$

Entonces, por la [[Desigualdad de Chabyshev]]:

$$ P(|\bar{X}_n - \mu| > \varepsilon) \leq \frac{\text{Var}(\bar{X}_n)}{\varepsilon^2} = \frac{\sigma^2}{n\varepsilon^2}. $$

Entonces:

$$ \lim_{n\to\infty} P(|\bar{X}_n - \mu| > \varepsilon) \leq \lim_{n\to\infty} \frac{\sigma^2}{n\varepsilon^2} = 0, $$

por lo tanto $$\displaystyle\lim_{n\to\infty} P(|\bar{X}_n - \mu| > \varepsilon) = 0\quad\square$$

(Recordar que la probabilidad siempre es no negativa.)