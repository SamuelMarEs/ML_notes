Sea $X$ una [[Variable aleatoria]]. Una función de variable aleatoria $X$ es una nueva variable aleatoria $Y = g(X)$.

Suponga que $X$ tiene una PDF $f_X$ y una CDF $F_X = P(X < x) = \displaystyle\int_{-\infty}^{x} f_X(t)\,dt$.

A su vez, $Y$ tiene sus propias PDF $f_Y$ y CDF $F_Y$.

La forma/algoritmo para obtener estas es, a groso modo:

$$ F_X \;\longrightarrow\; F_Y \;\longrightarrow\; f_Y. $$

**Ejemplo:** Suponga que tenemos $X \sim N(\mu, \sigma^2) \Rightarrow \overline{Y = aX + b}$.

Vamos primero a encontrar la CDF de $Y$:

$$
\begin{align*}
\text{CDF: } F_Y(y) = P(Y < y) &= P(aX + b < y) = P\!\left(X < \frac{y-b}{a}\right) \\
&= F_X\!\left(\frac{y-b}{a}\right).
\end{align*}
$$

Entonces podemos calcular la PDF de $Y$:

$$ 
f_Y(y) = \frac{d}{dy} F_Y\!\left(\frac{y-b}{a}\right) = \frac{1}{a}\,f_X\!\left(\frac{y-b}{a}\right)
= \frac{1}{a}\cdot\frac{1}{\sqrt{2\pi}\,\sigma}\,e^{-\dfrac{\left(\frac{y-b}{a}-\mu\right)^2}{2\sigma^2}}
= \frac{1}{\sqrt{2\pi}\,a\sigma}\,e^{-\dfrac{(y-(a\mu+b))^2}{2a^2\sigma^2}}.
$$

A partir de esto es posible derivar que $Y \sim N(a\mu + b,\; a^2\sigma^2)$.

### "Reescalado" de la [[Distribución Normal]] a $\mu=0$ y $\sigma=1$

Si tenemos una variable aleatoria $X \sim N(\mu, \sigma^2)$, podemos "trasladarla" a una variable con distribución $N(0,1)$.

Hoy en día, con el desarrollo de las computadoras, no suele ser necesario. La "función" que suele servir para esto es:

$$ \overline{Y} = \frac{X - \mu}{\sigma} \implies a = \frac{1}{\sigma},\quad b = -\frac{\mu}{\sigma}. $$