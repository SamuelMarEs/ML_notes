La distribución geométrica se utiliza para calcular la probabilidad del primer "éxito" en $n$ intentos  bajo una distribución Bernoulli ([[V.A. Bernoulli y binomial]]). Es decir, dada una secuencia de eventos Bernoulli con probabilidad $p$, ¿cuál es la probabilidad de que el primer éxito ocurra en el $n$-ésimo intento? $\to$ ([[Eventos independientes]])

$$
\begin{aligned}
P(\text{primer éxito en $n$-ésimo intento})
  &= P(F_1 \cap F_2 \cap \cdots \cap F_{n-1} \cap E_n) \\
  &\quad\text{(fallar $n-1$ veces)} \\
  &= P(F_1)\cdot P(F_2)\cdot\ldots\cdot P(F_{n-1})\cdot P(E_n) \\
  &= \underbrace{(1-p)\cdot(1-p)\cdot\ldots\cdot(1-p)}_{n-1\ \text{términos}}\cdot p
   = (1-p)^{n-1}\,p = q^{n-1}\,p.
\end{aligned}
$$

Entonces, dada una [[Variable aleatoria]], decimos que $X \sim \text{geométrica}(p) \iff P(X = k) = (1-p)^{k-1}\,p$.

**Ejemplo:** ¿Cuál es la probabilidad de que tome *al menos* 10 lanzamientos de dado para sacar 5?
**Forma 1:**

$$
X \sim \text{geométrica}\!\left(\tfrac{1}{6}\right). \qquad
P(X \geq 10) = P(X=10) + P(X=11) + P(X=12) + \cdots
$$

$$
= q^9 p + q^{10} p + q^{11} p + \cdots
= q^9 p\,\underbrace{(1 + q + q^2 + \cdots)}_{\text{serie geométrica}}
= q^9 p \cdot \frac{1}{1-q} = \frac{q^9 p}{p} = q^9 = \left(\frac{5}{6}\right)^9.
$$

**Forma 2:** $P(\text{primer éxito después del } 9^{\text{no}} \text{ intento})$ $= P(\text{ningún éxito en } 9 \text{ intentos})$:

$$
= \frac{5}{6}\cdot\frac{5}{6}\cdots\frac{5}{6} = \left(\frac{5}{6}\right)^9.
$$