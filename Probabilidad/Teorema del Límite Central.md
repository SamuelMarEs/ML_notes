Dada una secuencia de $n$ [[Variable aleatoria]]s independientes y con [[Distribuciones]] idénticas $X_1, X_2, \ldots, X_n$ tal que su [[Valor Esperado]] $E(X_i) = \mu$ y su [[Varianza y Desviación Estándar]] $\text{Var}(X_i) = \sigma^2$. Entonces la media muestral

$$ \bar{X}_n = \frac{1}{n}\sum_{i=1}^{n} X_i $$

va a seguir una [[Distribución Normal]], es decir que

$$ \bar{X}_n \sim N\!\left(\mu,\, \frac{\sigma^2}{n}\right). \qquad \left(\text{SD} = \frac{\sigma}{\sqrt{n}}\right) $$

Otra forma de plantear el teorema: Sea $S_n$ la suma de las variables aleatorias,

$$ S_n = \sum_{i=1}^{n} X_i, \quad \text{entonces} \quad S_n \sim N(n\mu,\, n\sigma^2). $$
Para la demostración, se utiliza la [[Función generadora de momentos]], y la [[Ley de los grandes números]], fundamentada en la [[Desigualdad de Markov]] y la [[Desigualdad de Chabyshev]]. Además entran conceptos de vital importancia como las [[Funciones de una variable aleatoria]]
Una forma un poco más formal de plantear el teorema es como sigue:

### **Teorema:** 
Sean $X_1, X_2, \ldots, X_n$ variables aleatorias idénticas e independientes con media $0$ y varianza $\sigma^2$, y sea $S_n = \displaystyle\sum_{i=1}^n X_i$. Entonces:

$$ \lim_{n\to\infty} P\!\left(\frac{S_n}{\sigma\sqrt{n}} \leq x\right) = \Phi(x), \quad \to \text{CDF de } N(0,1). $$

Enunciados equivalentes: $S_n \sim N(0, n\sigma^2)$, ó $\dfrac{1}{\sigma\sqrt{n}}S_n = \bar{X} \sim N(0, \sigma^2/n)$.

## **Demostración:**

**Paso 1:** Queremos mostrar que $Z = \dfrac{S_n}{\sigma\sqrt{n}} \sim N(0,1)$. Vamos a mostrar que tienen la misma función generadora de momentos. $m(t)$ para $N(0,1)$ es $e^{t^2/2}$.

**Paso 2:** Como todas las $X_i$ tienen la misma distribución, entonces tienen la misma función generadora de momentos $m(t)$. Sabemos que:

$$ m(S_n) = m(X_1)\,m(X_2)\cdots m(X_n) = \left[m(t)\right]^n. $$

**Paso 3:** Vamos a obtener la expansión de Taylor de $m(t)$:

$$ m(t) = \underbrace{m(0)}_{1} + \underbrace{t\,m'(0)}_{t\mu=0} + \frac{t^2}{2}\underbrace{m''(0)}_{\sigma^2} + \frac{t^3}{6}\underbrace{m'''(0)}_{E(t^3)} + \underbrace{\cdots}_{E(t^{2n})}. $$

**Paso 4:** Si $Y = bX$, entonces $m_Y(t) = m_X(bt)$. Por lo tanto tenemos que:

$$ m_Z(t) = m_{S_n}\!\left(\frac{t}{\sigma\sqrt{n}}\right) = \left[m\!\left(\frac{t}{\sigma\sqrt{n}}\right)\right]^n. $$

**Paso 5:**

$$ 
\begin{align*}
m\!\left(\frac{t}{\sigma\sqrt{n}}\right)
&= 1 + 0 + \frac{1}{2}\sigma^2\left(\frac{t^2}{\sigma^2 n}\right) + E\!\left(\frac{t^3}{\sigma^3 n^{3/2}}\right) + E\!\left(\frac{t^4}{\sigma^4 n^2}\right) + \cdots \\
&= 1 + \frac{1}{2}\cdot\frac{t^2}{n} + E\!\left(\frac{t^3}{\sigma^3 n^{3/2}}\right) + \cdots
\end{align*}
$$

**Paso 6:**

$$ 
\begin{align*}
\lim_{n\to\infty} m_Z(t)
&= \lim_{n\to\infty} \left[1 + \frac{1}{2}\cdot\frac{t^2}{n} + \varepsilon_n\right]^n
= \lim_{n\to\infty} \left(1 + \frac{t^2}{2n}\right)^n,
\end{align*}
$$

pues $\varepsilon_n$ tiende a cero.

Entonces, sea $u = \dfrac{2n}{t^2}$; si $n\to\infty$ entonces $u\to\infty$, $\dfrac{t^2}{2n} = \dfrac{1}{u}$ y $n = \dfrac{t^2}{2}u$.

Por lo tanto nos queda el siguiente límite:

$$ = \lim_{u\to\infty}\left(1 + \frac{1}{u}\right)^{\frac{t^2}{2}u}
= \left[\lim_{u\to\infty}\left(1 + \frac{1}{u}\right)^u\right]^{t^2/2}
= e^{t^2/2}. \qquad \square $$