Desigualdad importante para demostrar la [[Ley de los grandes números]].

Sean $E(X) = \mu$ y $\text{Var}(X) = \sigma^2$. Si $a > 0$, entonces:

$$ P(|X - \mu| \geq a) \leq \frac{\sigma^2}{a^2}. $$

#### **Demostración:** 
Sea $Y = (X-\mu)^2$ y $b = a^2$. Entonces:

$$ P(|X-\mu| \geq a) = P\!\left((X-\mu)^2 \geq a^2\right) = P(Y \geq b). $$

Notemos que $E(Y) = E\!\left[(X-\mu)^2\right] = \text{Var}(X) = \sigma^2$. Entonces por la [[Desigualdad de Markov]]:

$$ P(Y \geq b) \leq \frac{E(Y)}{b} = \frac{\text{Var}(X)}{a^2} = \frac{\sigma^2}{a^2}. \qquad \square $$