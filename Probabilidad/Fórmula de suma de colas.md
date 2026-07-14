Sea $X$ una [[Variable aleatoria]] no negativa. Entonces del [[Valor Esperado]] podemos decir que:

$$ E(X) = \sum_{k=1}^{n} P(X \geq k). $$

### **Demostración:** 
Sabemos que

$$
\begin{align*}
E(X) &= \sum_{k=1}^{n} k\,P(X=k) = 1\cdot P_1 + 2\cdot P_2 + 3\cdot P_3 + \cdots + (n-1)\cdot P_{n-1} + n\cdot P_n \\
&= P_1 + P_2 + P_3 + \cdots + P_{n-1} + P_n \quad \to P(X \geq 1) \\
&\quad + P_2 + P_3 + \cdots + P_{n-1} + P_n \quad \to P(X \geq 2) \\
&\quad + P_3 + \cdots + P_{n-1} + P_n \quad \to P(X \geq 3) \\
&\quad \vdots \\
&\quad + P_{n-1} + P_n \quad \to P(X \geq n-1) \\
&\quad + P_n \quad \to P(X \geq n)
\end{align*}
$$

$$ = \sum_{k=1}^{n} P(X \geq k). \qquad \square $$

(Recordar que $P(X \geq k) = 1 - P(X \leq k)$ — CDF.)