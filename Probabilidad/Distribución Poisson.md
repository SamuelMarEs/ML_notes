Si tenemos una [[Variable aleatoria]] que sigue una distribución normal, digamos para $n=1000$ intentos con una probabilidad $p=\frac{1}{1000}$. Entonces tenemos que  $X \sim N\!\left(1, \dfrac{999}{1000}\right)$. Sin embargo, podemos tomar la *PDF* de esta función entre -1 y 0, lo que nos daría casos negativos, que son físicamente imposibles.

Por esto se necesita una distribución distinta para la probabilidad muy grande o muy pequeña. Esto se hace en base a una distribución binomial ([[V.A. Bernoulli y binomial]]).

Sea $\lambda = np$, $X \sim \text{binomial}(n,p)$, entonces
$$
P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}.
$$
Si escribimos en términos de $\lambda$:

$$
P(X=k) = \frac{n!}{k!\,(n-k)!}\left(\frac{\lambda}{n}\right)^k\!\left(1 - \frac{\lambda}{n}\right)^{n-k}
= \frac{\lambda^k}{k!}\cdot\frac{n(n-1)(n-2)\cdots(n-k+1)}{n^k}
  \cdot\left(1-\frac{\lambda}{n}\right)^n\!\left(1-\frac{\lambda}{n}\right)^{-k}.
$$

Entonces, cuando $n \to \infty$, tenemos:

$$
\lim_{n\to\infty} \frac{\lambda^k}{k!}\cdot
\underbrace{\frac{n(n-1)(n-2)\cdots(n-k+1)}{n^k}}_{\to\, 1}
\cdot\underbrace{\left(1-\frac{\lambda}{n}\right)^n}_{\to\, e^{-\lambda}}
\cdot\underbrace{\left(1-\frac{\lambda}{n}\right)^{-k}}_{\to\, 1}
= \frac{\lambda^k}{k!}\cdot e^{-\lambda}.
$$

Esta distribución es sobre todo usada para eventos "raros".