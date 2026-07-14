Dos eventos $A$ y $B$ son **independientes** si saber que uno ocurre no provee información extra sobre el otro, es decir:
$$
P(A \mid B) = P(A), \qquad \text{y} \qquad P(B \mid A) = P(B).
$$

**Corolario:** $P(A \cap B) = P(A) \cdot P(B)$.
Este corolario bastante sencillo está basado en la [[Probabilidad condicional]].
**Demostración:**

Como $P(A) = P(A \mid B) \Rightarrow P(A) = \dfrac{P(A \cap B)}{P(B)} \Rightarrow P(A)\,P(B) = P(A \cap B)$. $\quad\square$

**Ejemplo:**
$$
A = \text{corazón}, \quad P(A) = \tfrac{1}{4}; \qquad B = \text{reina Q}, \quad P(B) = \tfrac{1}{13}.
$$

$$
\Rightarrow P(A \cap B) = P(A)\,P(B) = \frac{1}{4} \cdot \frac{1}{13} = \frac{1}{52} \quad \text{(reina de corazones)}.
$$

$$
P(A \mid B) = \frac{1}{4}, \qquad P(B \mid A) = \frac{1}{13}.
$$