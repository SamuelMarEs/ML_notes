### Distribución Marginal
Al trabajar con [[Probabilidad Conjunta]], si tenemos una PDF dada por $f(x,y)$, entonces la _distribución marginal_ está dada por:

$$ f_X(x) = \int_{-\infty}^{\infty} f(x,y)\,dy. $$

Esta nos da una función de probabilidad que únicamente depende de $x$. De forma análoga:

$$ f_Y(y) = \int_{-\infty}^{\infty} f(x,y)\,dx. $$

Para distribuciones discretas (Bernoulli, Binomial, Poisson), tenemos:

$$ P_X(x) = \sum_{j} P(X=x,\; Y=y_j), \qquad \to y_j \text{ constante.} $$
Esto nos permite trabajar independientemente con cada [[Variable aleatoria]].
### Distribución Condicional
Para la **distribución condicional**, la idea es en esencia la misma que con la [[Probabilidad condicional]] de dos eventos. Recordemos que

$$ P(A \mid B) = \frac{P(A \cap B)}{P(B)}, $$

pero en este caso no tratamos con eventos, sino con [[Variable aleatoria]] $X$ y $Y$. De cierta forma, $A \Rightarrow X=x$ y $B \Rightarrow Y=y$, y $P(A \cap B)$ es la probabilidad de que sucedan simultáneamente, i.e., $P(x,y)$. Entonces tenemos que:

$$ P(X=x \mid Y=y) = \frac{P(x,y)}{P_Y(y)}. \qquad \to \text{dist. discreta.} $$

De forma análoga tenemos para distribuciones continuas:

$$ f_{Y \mid X}(y \mid x) = \frac{f(x,y)}{f_X(x)}. \qquad \to \text{dist. continua.} $$