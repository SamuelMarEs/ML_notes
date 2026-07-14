La función generadora de momentos, es una función que lleva al [[Valor Esperado]], la [[Varianza y Desviación Estándar]], y así en adelante.:
$$ \text{media: } E(X) = \mu, \qquad \text{varianza: } E(X^2) - [E(X)]^2 = \sigma^2, \qquad \text{"momentos": } E(X^n). $$

$$ m(t) = \begin{cases}
\displaystyle\sum_{x} e^{tx}\,P(X=x), & X \text{ discreta} \\[8pt]
\displaystyle\int_{-\infty}^{\infty} e^{tx}\,f(x)\,dx, & X \text{ continua}
\end{cases}
\quad \to \text{Transformada de Laplace.} $$
Esta función es importante pues da un método de encontrar los momentos de cualquier [[Variable aleatoria]].

### **Teorema:** 
Dada la función generadora de momentos, $m^{(n)}(0) = E(X^n)$.

$m(t)$ determina de forma única la CDF, $P(X \leq x)$.

### Ejemplo 1: $X \sim \text{Poisson}(\lambda)$

$$
\begin{align*}
m(t) &= \sum_k e^{tk}\,\frac{\lambda^k e^{-\lambda}}{k!} = e^{-\lambda}\sum_k \frac{(e^t \lambda)^k}{k!} = e^{-\lambda}\,e^{\lambda e^t} = e^{\lambda(e^t - 1)}.
\end{align*}
$$

### Ejemplo 2: $X \sim N(0,1)$

$$
\begin{align*}
m(t) &= \int_{-\infty}^{\infty} e^{tx}\,\frac{1}{\sqrt{2\pi}}\,e^{-x^2/2}\,dx = \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} e^{tx - x^2/2}\,dx.
\end{align*}
$$

Observemos que:

$$ \frac{x^2}{2} - tx = \frac{1}{2}(x^2 - 2tx) = \frac{1}{2}(x-t)^2 - \frac{t^2}{2}. $$

Entonces:

$$
\begin{align*}
m(t) &= \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} e^{-\frac{1}{2}(x-t)^2 + \frac{t^2}{2}}\,dx = e^{t^2/2}\,\underbrace{\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} e^{-\frac{1}{2}(x-t)^2}\,dx}_{N(t,\,1)} = e^{t^2/2}.
\end{align*}
$$

### Ejemplo 3: $X \sim \text{exponencial}(\lambda)$

$$
\begin{align*}
m(s) &= \int_0^{\infty} e^{st}\,\lambda e^{-\lambda t}\,dt = \lambda\int_0^{\infty} e^{(s-\lambda)t}\,dt = \frac{\lambda}{s-\lambda}\,e^{(s-\lambda)t}\Big|_0^{\infty} \qquad (\text{para } s < \lambda) \\
&= \frac{\lambda}{\lambda - s}.
\end{align*}
$$

### Teorema: $m^{(n)}(0) = E(X^n)$

**Demostración:**

$$ m(t) = \int_{-\infty}^{\infty} e^{tx}\,f(x)\,dx \implies m'(t) = \int_{-\infty}^{\infty} x\,e^{tx}\,f(x)\,dx. $$

Entonces $m'(0) = \displaystyle\int_{-\infty}^{\infty} x\,f(x)\,dx = E(X)$, $\ldots$, $m^{(n)}(t) = \displaystyle\int_{-\infty}^{\infty} x^n\,e^{tx}\,f(x)\,dx$,

$$ \Rightarrow m^{(n)}(0) = \int_{-\infty}^{\infty} x^n\,f(x)\,dx = E(X^n) \quad \text{por definición.} \qquad \square $$

### Ejemplo: $X \sim \text{Poisson}(\lambda)$

$$ m(t) = e^{\lambda(e^t-1)} \implies m'(t) = e^{\lambda(e^t-1)}\cdot\lambda e^t. $$

$$ \Rightarrow E(X) = m'(0) = \lambda. $$

$$ m''(t) = e^{\lambda(e^t-1)}\cdot(\lambda e^t)^2 + e^{\lambda(e^t-1)}\cdot\lambda e^t. $$

$$ \Rightarrow E(X^2) = m''(0) = \lambda^2 + \lambda \implies \text{Var}(X) = E(X^2) - [E(X)]^2 = \lambda. $$

# Propiedad Aditiva de la Función Generadora de Momentos

Sean $X$, $Y$ variables aleatorias independientes. Sean $m_X$ y $m_Y$ sus funciones generadoras de momentos. Si definimos $Z = X + Y$, entonces:

$$ m_Z(t) = m_X(t) \cdot m_Y(t). $$

**Demostración:**

$$ 
\begin{align*}
m_Z(t) = E(e^{tZ}) &= E\!\left(e^{t(X+Y)}\right) = E\!\left(e^{tX}\,e^{tY}\right) = E(e^{tX})\,E(e^{tY}) = m_X(t)\,m_Y(t). \qquad \square
\end{align*} 
$$