## Coeficientes Binomiales

$$
\binom{n}{r} = \frac{n!}{r!(n-r)!}
$$

\# de muestras de tamaño $r$ de $n$ elementos. No ordenadas, sin repetición.

$$
(x+y)^n = \sum_{k=0}^{n} \binom{n}{k} x^k y^{n-k}
$$

Triángulo de Pascal (coeficiente $n$):
![[TrianguloPascal.png]]

En este coeficiente $\binom{n}{k}$ se basa la distribución binomial ([[V.A. Bernoulli y binomial]]).
## Coeficiente Multinomial

$n$ objetos divididos en $r$ clases de tamaño $n_1, n_2, \ldots, n_r$ (el orden no importa).

$$
\binom{n}{n_1, n_2, \ldots, n_r} = \frac{n!}{n_1!\, n_2!\, \cdots\, n_r!}
$$

\# total de muestras de esta forma, asumiendo $n = n_1 + n_2 + \cdots + n_r$.

**Demostración:**

$$
\binom{n}{n_1, n_2, \ldots, n_r}
= \binom{n}{n_1}\binom{n-n_1}{n_2}\binom{n-n_1-n_2}{n_3}\cdots\binom{n-n_1-\cdots-n_{r-1}}{n_r}
$$

$$
= \frac{n!}{n_1!\,(n-n_1)!}\cdot\frac{(n-n_1)!}{n_2!\,(n-n_1-n_2)!}\cdot\frac{(n-n_1-n_2)!}{n_3!\,(n-n_1-n_2-n_3)!}\cdots\frac{(n-\cdots-n_{r-1})!}{n_r!\,(n-\cdots-n_r)!}
$$

$$
= \frac{n!}{n_1!\, n_2!\, \cdots\, n_r!} \qquad (\text{ya que } 0! = 1).
$$
En este coeficiente se basa la [[Distribución multinomial]].