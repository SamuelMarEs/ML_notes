## Probabilidad Condicional

Sean $A$, $B$ dos eventos posibles en un experimento aleatorio. ¿Cuál es la probabilidad de $A$ *dado* $B$? Es decir, $B$ ya ocurrió.

$$
\Rightarrow P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

¿Cómo se calcula $P(B \mid A)$?

**Ejemplo:** $A$: primer dado $= 3$; $B$: segundo dado $= 5$; $C$: suma de dados $= 6$.

$A$ y $B$ son eventos independientes, i.e. $P(A \mid B) = P(A) = \tfrac{1}{6}$. Pero $P(C \mid A) = ?$

$$
|\Omega| = 36 \text{ posibilidades } (x_i, x_j), \quad
|A| = 6 \text{ posibilidades } (3,x), 
$$
$$
|C| = 5 \text{ posibilidades } \{(1,5),(2,4),(3,3),(4,2),(5,1)\}.
$$

$$
P(C \mid A) = \frac{P(C \cap A)}{P(C)} = \frac{\tfrac{1}{36}}{\tfrac{5}{36}} = \frac{1}{5} 
$$

**Corolario (Ley de la multiplicación):**
$$
P(A \cap B) = P(A \mid B)\, P(B)
$$

## Ley de Probabilidad Total

Sea $\Omega = \displaystyle\bigcup_{i=1}^{n} B_i$ (o sea, $\Omega$ tiene una partición en $B_1, B_2, \ldots, B_n$), tal que $B_i \cap B_j = \varnothing$ si $i \neq j$.

Entonces la probabilidad de un evento $A$ está dada por:

$$
P(A) = \sum_{i=1}^{n} P(A \mid B_i)\, P(B_i) = \sum_{i=1}^{n} P(A \cap B_i).
$$