El valor esperado puede verse como el "centro de masa" de una PDF sobre una [[Variable aleatoria]] $X$.

$$ E(X) = \sum_{k} x_k\, P(X = x_k). \qquad \to \text{para dist. discreta.} $$

Y para distribuciones continuas tenemos la expresión:

$$ E(X) = \int_{-\infty}^{\infty} x\, f(x)\,dx. \qquad \to \text{para dist. continua.} $$

Si tomo una muestra $X_j$ $n$ veces, y calculo la media, entonces tenemos que

$$ \bar{X} = \frac{1}{n}\sum_{j=1}^{n} X_j \qquad \text{(media de la muestra)}. $$

Esta media va a cumplir que $\displaystyle\lim_{n\to\infty} X \to \mu = E(X)$, lo que se conoce como la [[Ley de los grandes números]].

### Definiciones

- **Moda:** Valor más posible, o con mayor probabilidad de aparecer. $x$ tal que $P(x)$ es el máximo.
- **Media/Promedio:** Es el valor esperado. "Promedio con peso". $E(X) = \mu$.
- **Mediana:** Valor exactamente en la mitad de la distribución. $x$ tal que la CDF $F(x) = \frac{1}{2}$.

### Propiedades del Valor Esperado

**1.** Sean $X$ y $Y$ variables aleatorias, entonces $E(X + Y) = E(X) + E(Y)$.

**Demostración:** Tenemos que

$$
\begin{align*}
E(X+Y) &= \sum_y \sum_x (x+y)\,P(x,y)
= \sum_y \sum_x x\,P(x,y) + \sum_y \sum_x y\,P(x,y) \\
&= \sum_x x\,P(x) + \sum_y y\,P(y) = E(X) + E(Y). \qquad \to \text{dist. discreta.} \quad \square
\end{align*}
$$

Si son distribuciones continuas, entonces tenemos:

$$
\begin{align*}
E(X+Y) &= \iint_{y\,x} (x+y)\,f(x,y)\,dx\,dy
= \iint_{y\,x} x\,f(x,y)\,dx\,dy + \iint_{y\,x} y\,f(x,y)\,dx\,dy \\
&= \int_x x\,f(x)\,dx + \int_y y\,f(y)\,dy = E(X) + E(Y). \qquad \square
\end{align*}
$$

**2.** Si $X$ y $Y$ son _independientes_, entonces $E(XY) = E(X)\,E(Y)$.

**Demostración:** Dados $X$, $Y$ independientes, entonces

$$ E(XY) = \sum_x \sum_y xy\,P(x,y). $$

Como $X$, $Y$ son independientes, entonces

$$ \sum_x \sum_y xy\,P(x,y) = \sum_x \sum_y xy\,P(x)\,P(y) = \sum_x x\,P(x)\sum_y y\,P(y) = E(X)\cdot E(Y). \quad \square $$

La demostración para distribuciones continuas es análoga.

**3.** Si $Y$ es una función de variable aleatoria, i.e. $Y = g(X)$, entonces

$$ E(Y) = E(g(X)) = \sum_x g(x)\,P(x) \qquad \to \text{dist. discreta,} $$

$$ = \int_{-\infty}^{\infty} g(x)\,f(x)\,dx. \qquad \to \text{dist. continua.} $$

**Ejemplo (propiedad 3):**

$$ E(X^2) = \int_{-\infty}^{\infty} x^2\,f(x)\,dx. $$