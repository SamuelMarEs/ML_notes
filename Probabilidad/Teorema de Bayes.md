El *Teorema de Bayes* es un teorema importante sobre la [[Probabilidad condicional]].
Sabemos que
$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}, \qquad \text{y que} \qquad P(A \cap B) = P(A \mid B)\,P(B).
$$

Pero lo que queremos saber es $P(B \mid A)$. Este es un problema *inverso*.

$$
P(B \mid A) = \frac{P(A \mid B)\,P(B)}{P(A)} = \frac{P(A \mid B)\,P(B)}{P(A \mid B)\,P(B) + P(A \mid B^c)\,P(B^c)}
$$

**Demostración:** Sabemos que
$$
P(B \mid A) = \frac{P(B \cap A)}{P(A)} = \frac{P(A \cap B)}{P(A)}.
$$
Entonces podemos multiplicar por $1 = \dfrac{P(B)}{P(B)}$:

$$
P(B \mid A) = \frac{P(A \cap B)}{P(A)} \cdot \frac{P(B)}{P(B)} = \frac{P(A \cap B) \cdot P(B)}{P(B) \cdot P(A)} = \frac{P(A \mid B)\,P(B)}{P(A)}. \qquad \square
$$

$P(B \mid A)$: *posterior*,  $P(B)$: *a priori*,  $P(A \mid B)$: *actualización*.

### Ejemplo 1 (enfermedad rara)

Suponga que tenemos un test con 99\% de certeza, pero la enfermedad es muy rara y sólo el 0.001\% de la población la tiene. ¿Cuál es la probabilidad de tenerla si tu test fue positivo?

- $A$ = test positivo
- $B$ = tener la enfermedad

Datos:
$$
P(A \mid B) = 0.99, \quad P(A \mid B^c) = 0.01, \quad P(B) = 0.001, \quad P(B^c) = 0.999.
$$

Entonces:
$$
P(B \mid A) = \frac{P(A \mid B)\,P(B)}{P(A \mid B)\,P(B) + P(A \mid B^c)\,P(B^c)}
= \frac{(0.99)(0.001)}{(0.99)(0.001) + (0.01)(0.999)}
= \frac{11}{122} \approx 0.0901 \approx 9\%.
$$

### Ejemplo 2 (test de droga)

Suponga que tenemos un test con 90\% de certeza para una droga que usa el 10\% de la población. ¿Cuál es la probabilidad de usar la droga dado un test positivo?

Sean $B$: usar la droga, $A$: resultado del test. $P(\text{usar}) = 0.1$.

$$
P(+\mid \text{usa}) = 0.9, \qquad P(-\mid \text{no usa}) = 0.9. \qquad \text{Queremos } P(\text{usa la droga} \mid +).
$$

$$
P(\text{usar} \mid +) = \frac{P(+ \mid \text{usar})\,P(\text{usar})}{P(+ \mid \text{usar})\,P(\text{usar}) + P(+ \mid \text{no usar})\,P(\text{no usar})}
$$

donde $P(+ \mid \text{no usar}) = 0.1$ y $P(\text{no usar}) = 0.9$:

$$
= \frac{(0.9)(0.1)}{(0.9)(0.1) + (0.1)(0.9)} = \frac{1}{2} = 0.5.
$$

**Caso 2:** Suponga $P(+ \mid \text{usa}) = 0.9$ (*sensitividad*), pero $P(- \mid \text{no usa}) = 0.8$ (*especificidad*), por lo que $P(+ \mid \text{no usa}) = 0.2$.

Entonces:
$$
P(\text{usa} \mid +) = \frac{P(+ \mid u)\,P(u)}{P(+ \mid u)\,P(u) + P(+ \mid \text{no})\,P(\text{no})}
= \frac{(0.9)(0.1)}{(0.9)(0.1) + (0.2)(0.9)} = \frac{1}{3}.
$$