[[V.A. Bernoulli y binomial]]:
1. Bernoulli: Una [[Variable aleatoria]] se dice es Bernoulli, si únicamente puede tomar dos valores, 0 para fracasos, y 1 para éxitos.
   $$X \sim \text{Bernoulli} \iff X\in\{0,1\}.$$
2. Binomial: La distribución binomial se emplea para calcular la probabilidad de obtener $k$ éxitos en $n$ eventos Bernoulli.
   $$X \sim \text{binomial}(n,p) \iff P(X=k)=\binom{n}{k}p^k(1-p)^k.$$

[[Distribución Normal]]:
La distribución normal es una "generalización" o el límite de la distribución binomial. Utilizada para un número de eventos $n$ muy grande, y una probabilidad $p$ no muy pequeña. Sus parámetros son la media $\mu=np$ y la desviación estándar cuadrada $\sigma^2=npq$. 
$$
X \sim \text{normal}(np,\, npq)=\text{normal}(\mu, \sigma ^2)
\implies
P(X = x) = \frac{1}{\sqrt{2\pi}\,\sigma}\,e^{-\frac{(x-\mu)^2}{2\sigma^2}}.
$$

[[Distribución Poisson]]:
Al igual que la distribución normal, es un límite para la distribución binomial, solo que en este caso, es utilizada para eventos "raros", *i.e.* con una baja probabilidad. Su único parámetro es $\lambda = np$.
$$
X \sim \text{Poisson}(\lambda) \implies P(X=k) = \frac{\lambda^k}{k!}\cdot e^{-\lambda}.
$$

[[Distribución Geométrica]]:
Utilizada para determinar la probabilidad de que el primer éxito en una serie de eventos Bernoulli ocurra en el $n$-ésimo intento.
$$
X \sim \text{geométrica}(p) \iff P(X = k) = (1-p)^{k-1}\,p.
$$

[[Distribución Exponencial]]:
Usada para estimar el tiempo para que ocurra un evento raro (Poisson). Algunos ejemplos son el decaimiento radioactivo o la vida útil de una bombilla. 
Sea $T$ un tiempo aleatorio, decimo que:
$$
T \sim \text{exponencial}(\lambda) \implies 
P(T = t) = \begin{cases} \lambda e^{-\lambda t}, & t \geq 0 \\ 0, & t < 0 \end{cases}, \quad \text{donde} \quad
\lambda = \frac{1}{\text{tiempo promedio}}.
$$
Para la distribución exponencial, es relevante destacar que existe una función explícita para su *CDF* (función de distribución acumulada), dada por:
$$
F(t) = \int_{-\infty}^{t} P(t)\,dt = \cdots = 1 - e^{-\lambda t}.
$$
[[Distribución Gamma]]:

[[Distribución Chi-Cuadrada]]:

[[Distribuciones Marginal y Condicional]]:
