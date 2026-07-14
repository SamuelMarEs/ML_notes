$n$ = total de objetos, $K$ = objetos defectuosos, $r$ = muestra de $n$, $m$ = # defectuosos en $r$.

**¿$P(r$ muestras con $m$ defectuosos)?**

$$
r = m \text{ defectuosos} + (r-m) \text{ no defectuosos}, \qquad n = K + (n-K)
$$

- $\binom{r}{m}$: # de muestras de tamaño $r$ de $n$.
- $\binom{K}{m}$: # de formas de elegir $m$ de $K$ objetos defectuosos.
- $\binom{n-K}{r-m}$: # de formas de elegir objetos NO defectuosos.

$$
\Rightarrow P(m \text{ defectuosos en } r \text{ muestras}) = \frac{\dbinom{K}{m}\dbinom{n-K}{r-m}}{\dbinom{n}{r}}
$$

**Generalización: [[Distribución multinomial]].**

Sea $N = G + B$ con $\binom{G=\text{good}}{B=\text{bad}}$ y $n = g + b$:

$$
P = \frac{\dbinom{G}{g} \cdot \dbinom{B}{b}}{\dbinom{N}{n}}
$$