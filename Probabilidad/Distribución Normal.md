Una [[Variable aleatoria]] que sigue una distribución normal, se puede decir que es el límite de la distribución binomial ([[V.A. Bernoulli y binomial]]).

(Para $n$ grande y $npq$ no muy pequeño.)

**Binomial:**
$$
P(X=k) = \binom{n}{k} p^k q^{n-k}, \qquad X \sim \text{binomial}(n,p).
$$
\# de éxitos en $n$ intentos Bernoulli independientes, $X = B_1 + \cdots + B_n$, donde $B_i \sim \text{Bernoulli}(p)$.

**Normal:**
$$
X \sim \text{normal}(np,\, npq)
\implies
P(X = x) = \frac{1}{\sqrt{2\pi}\,\sigma}\,e^{-\frac{(x-\mu)^2}{2\sigma^2}}.
$$
Se suele escribir $N(\mu, \sigma^2)$, donde $\mu$ es la media/mediana y $\sigma^2$ es la varianza cuadrática/desviación estándar cuadrada.

Para $p$ ó $q$ pequeños, la distribución normal comienza a dar valores negativos, que no es físicamente posible. Para esto existe la [[Distribución Poisson]].

### Distribución Normal Estándar / Unidad Normal

En base a la distribución normal, se define la distribución normal estándar/unidad normal, cuando $\mu = 0,\; \sigma = 1$.

$$
P(-1 \leq X \leq 1) = \int_{-1}^{1} f(x)\,dx = \Phi(1) - \Phi(-1).
$$

$$
\text{CDF} = \textit{Cumulative Density Function} = \int_{-\infty}^{x} f(t)\,dt = \Phi(x).
$$

$$
P(a \leq X \leq b) = \int_{a}^{b} f(x)\,dx.
$$

### Ejemplo: Aproximación Normal a la Binomial

Suponga que lanzamos una moneda 400 veces, con probabilidad $p = 1/2$.

$$
\#\text{soles} = X \sim \text{binomial}(400,\, \tfrac{1}{2}). \qquad \text{¿}P(190 \leq X \leq 230)\text{?}
$$

$$
P(190 \leq X \leq 230) = P(190) + P(191) + \cdots + P(229) + P(230)
\quad \Rightarrow \text{ usando la dist. binomial.}
$$

Con una distribución normal:
$$
X \sim \text{normal}(np,\, npq) = \text{normal}\!\left(\frac{400}{2},\, \frac{400}{4}\right) = \text{normal}(200,\, 100).
$$

$$
P(190 \leq X \leq 230) = \int_{190}^{230} f(x)\,dx,
\quad \text{donde } f(x) = \frac{1}{\sqrt{2\pi}\,\sigma}\,e^{-\frac{(x-\mu)^2}{2\sigma^2}},
\quad \mu = 200,\ \sigma^2 = 100,\ \sigma = 10.
$$

$$
= \Phi(230) - \Phi(190), \qquad \text{donde } \Phi(y) = \int_{-\infty}^{y} f(\theta)\,d\theta.
$$