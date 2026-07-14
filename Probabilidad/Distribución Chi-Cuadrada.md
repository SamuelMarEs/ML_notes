Sea $X \sim N(0,1)$ ([[Distribución Normal]]) una [[Variable aleatoria]], y $Y = X^2$; decimos que $Y$ sigue una distribución **Chi-cuadrada**. Muy usada en estadística.

Sea $F_Y$ la CDF de $Y$, entonces:

$$
\begin{align*}
F_Y(y) = P(Y < y) &= P(X^2 < y) = P(|X| < \sqrt{y}) \\
&= P(-\sqrt{y} < X < \sqrt{y}).
\end{align*}
$$

Sea $F_X(x) = \Phi(x)$ la CDF de $X$, entonces tenemos que:

$$ P(-\sqrt{y} < X < \sqrt{y}) = \Phi(\sqrt{y}) - \Phi(-\sqrt{y}). $$

Entonces la PDF de $Y$ va a estar dada por:

$$ f_Y(y) = \frac{d}{dy}\!\left[\Phi(\sqrt{y}) - \Phi(-\sqrt{y})\right]
= \Phi'(\sqrt{y})\cdot\frac{1}{2\sqrt{y}} + \Phi'(-\sqrt{y})\cdot\frac{1}{2\sqrt{y}}. $$

Como la PDF de $X$, $f_X(x) = \Phi'(x)$, es una función par (para $X \sim N(0,1)$), entonces $\Phi'(\sqrt{y}) = \Phi'(-\sqrt{y})$, por lo tanto:

$$ f_Y(y) = y^{-1/2}\,\Phi'(\sqrt{y}) = y^{-1/2}\,f_X(\sqrt{y}). $$

Como $X \sim N(0,1) \Rightarrow f_X(y) = \dfrac{1}{\sqrt{2\pi}}\,e^{-y/2}$, entonces:

$$ f_Y(y) = \frac{y^{-1/2}\,e^{-y/2}}{\sqrt{2\pi}}. \qquad (\Rightarrow Y \sim N(0, \sqrt{y})\text{?}) $$