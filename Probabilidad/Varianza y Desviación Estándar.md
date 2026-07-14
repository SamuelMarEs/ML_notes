Si el [[Valor Esperado]] $\mu = E(X)$ mide el "centro de masa" de una PDF para una [[Variable aleatoria]] $X$, entonces la varianza $\text{Var}(X)$ mide el promedio del cuadrado de las desviaciones (qué tan lejos está) de $X$ respecto a $\mu$.

La desviación estándar $\text{SD}(X)$ mide la "extensión" del histograma:

$$ \text{SD}(X) = \sqrt{\text{Var}(X)}. $$

$$ \text{Var}(X) = E\!\left[(X-\mu)^2\right]. $$

Se puede demostrar que esto es igual a $E(X^2) - [E(X)]^2$.

**Demostración:**

$$
\begin{align*}
\text{Var}(X) &= E\!\left[(X-\mu)^2\right] = E\!\left[X^2 - 2\mu X + \mu^2\right] \\
&= E(X^2) + E(-2\mu X) + E(\mu^2) \\
&= E(X^2) - 2\mu E(X) + \mu^2 \qquad (\mu^2 \text{ constante},\ {-2\mu E(X) = -2\mu^2}) \\
&= E(X^2) - 2\mu^2 + \mu^2 = E(X^2) - \mu^2 \\
&= E(X^2) - \left[E(X)\right]^2. \qquad \square
\end{align*}
$$

Desviación estándar: $\text{SD}(X) = \sigma$ y $\text{Var}(X) = \sigma^2$.

### Ejemplo: $T \sim \text{exponencial}(\lambda)$, $f(t) = \lambda e^{-\lambda t}$
En este ejemplo tenemos una [[Distribución Exponencial]], y vamos a calcular la media, varianza, desviación estándar y mediana
#### **Media:**

$$ E(T) = \int_{-\infty}^{\infty} t\,f(t)\,dt = \int_0^{\infty} t\,\lambda e^{-\lambda t}\,dt. $$

Por partes: $u = t$, $dv = \lambda e^{-\lambda t}\,dt$, $du = dt$, $v = -e^{-\lambda t}$. Entonces:

$$
\begin{align*}
\int_0^{\infty} t\,\lambda e^{-\lambda t}\,dt
&= \left[-t e^{-\lambda t}\right]_0^{\infty} - \int_0^{\infty} -e^{-\lambda t}\,dt
= 0 + \int_0^{\infty} e^{-\lambda t}\,dt \\
&= \left[-t e^{-\lambda t}\right]_0^{\infty} + \left(-\frac{e^{-\lambda t}}{\lambda}\right)_0^{\infty} \\
&= 0 + \left(0 - \left(-\frac{1}{\lambda}\right)\right) = \frac{1}{\lambda}.
\end{align*}
$$

#### **Varianza:**

Para la varianza, sabemos que $\text{Var}(T) = E(T^2) - [E(T)]^2$, donde $E(T) = \frac{1}{\lambda}$, y tenemos que:

$$ E(T^2) = \int_0^{\infty} t^2\,f(t)\,dt = \cdots = \frac{2}{\lambda^2}, $$

por lo tanto:

$$ \text{Var}(T) = \frac{2}{\lambda^2} - \left(\frac{1}{\lambda}\right)^2 = \frac{1}{\lambda^2}. $$

#### **Desviación Estándar:**
Una vez que conocemos la varianza, podemos calcular la desviación estándar:

$$ \text{SD}(T) = \sqrt{\text{Var}(T)} = \frac{1}{\lambda}. $$

#### **Mediana:**

También podemos calcular la mediana, i.e. el valor para el cual la CDF $= \frac{1}{2}$. Es decir:

$$ \int_0^{x} f(t)\,dt = \int_0^{x} \lambda e^{-\lambda t}\,dt = 1 - e^{-\lambda x} = \frac{1}{2}, $$

lo que implica que:

$$ e^{-\lambda x} = \frac{1}{2} \implies -\lambda x = \ln\!\left(\frac{1}{2}\right)
\implies \boxed{x = \frac{\ln(2)}{\lambda}.} \quad \to \text{Mediana}(T). $$

### Ejemplo: $E(aX+b)$ y $\text{Var}(aX+b)$, $Y = aX+b$

Supongamos que tenemos $X$ en $^\circ$C y queremos cambiar a $^\circ$F ($a = 9/5$, $b = 32$).

Supongamos que $X$ es continua. Entonces:

$$ E(aX+b) = \int_{-\infty}^{\infty}(ax+b)\,f(x)\,dx = a\underbrace{\int_{-\infty}^{\infty} x\,f(x)\,dx}_{E(X)} + b\underbrace{\int_{-\infty}^{\infty} f(x)\,dx}_{1} = aE(X)+b. $$

($E(X)$ es una función lineal.)

Ahora vamos a calcular:

$$
\begin{align*}
\text{Var}(aX+b) = \text{Var}(Y) &= E\!\left[\bigl(Y - E(Y)\bigr)^2\right], \quad \text{sustituyendo:} \\
&= E\!\left[\bigl(aX+b - aE(X)-b\bigr)^2\right] = E\!\left[a^2\bigl(X-E(X)\bigr)^2\right] = a^2\,\text{Var}(X).
\end{align*}
$$

### Ejemplo: Distribución de Maxwell

Suponga $X$ = magnitud de velocidad de una molécula de gas:

$$ f(x) = \sqrt{\frac{2}{\pi}}\,\frac{x^2\,e^{-x^2/2\sigma^2}}{\sigma^3}. $$

Esta se conoce como la distribución de Maxwell. Si $Y = \frac{1}{2}mX^2$ (energía cinética), ¿qué es $E(Y)$?

$$
\begin{align*}
E(Y) &= \int_0^{\infty} \frac{1}{2}mx^2\,f(x)\,dx = \frac{m}{2}\sqrt{\frac{2}{\pi}}\,\frac{1}{\sigma^3}\int_0^{\infty} x^4\,e^{-x^2/2\sigma^2}\,dx.
\end{align*}
$$

Cambio de variable $u = \dfrac{x^2}{2\sigma^2}$:

$$ \cdots = \frac{2m\sigma^2}{\sqrt{\pi}}\int_0^{\infty} u^{3/2}\,e^{-u}\,du = \frac{2m\sigma^2}{\sqrt{\pi}}\,\Gamma\!\left(\frac{5}{2}\right) \quad \to \text{función gamma.} $$

$$ \cdots = \frac{3}{2}m\sigma^2. \qquad \text{(Temperatura del gas.)} $$