Resultado importante para probar la [[Desigualdad de Chabyshev]].

Sea $X \geq 0$, entonces:
$$ P(X \geq a) \leq \frac{E(X)}{a}. $$

#### **Demostración:** 
Observemos que

$$ E(X) = \sum_x x\,P(X=x) \geq \sum_{x \geq a} x\,P(X=x) \geq \sum_{x \geq a} a\,P(X=x) = a\,P(X \geq a), $$

por lo tanto $\dfrac{E(X)}{a} \geq P(X \geq a)$. $\quad\square$

**Ejemplo:** Supongamos $E(X) = 10$, entonces $P(X \geq 20) \leq \dfrac{1}{2}$.