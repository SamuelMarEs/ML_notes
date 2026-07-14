Una [[Variable aleatoria]] que sigue una distribución exponencial es usada para estimar el tiempo para que un evento raro ([[Distribución Poisson]]) ocurra.
Sea $T$ un tiempo aleatorio, decimos que $T \sim \text{exponencial}(\lambda)$ si:

$$
\lambda = \frac{1}{\text{tiempo promedio}}, \qquad
P(T = t) = \begin{cases} \lambda e^{-\lambda t}, & t \geq 0 \\ 0, & t < 0 \end{cases}
$$

**Ejercicio: Derivar la CDF.**
$$
F(t) = \int_{-\infty}^{t} P(t)\,dt = \cdots = 1 - e^{-\lambda t}.
$$

Sea $P(t) = \begin{cases} \lambda e^{-\lambda t}, & t \geq 0 \\ 0, & t < 0 \end{cases}$, entonces:

$$
\begin{aligned}
\int_{-\infty}^{t} P(x)\,dx
  &= \int_{-\infty}^{0} 0\,dx + \int_{0}^{t} \lambda e^{-\lambda x}\,dx
   = 0 + \int_{0}^{t} \lambda e^{-\lambda x}\,dx \\
  &\quad (u = -\lambda x,\ du = -\lambda\,dx \implies x\to 0,\ u\to 0;\ x\to t,\ u\to -\lambda t) \\
  &= -\int_{\lambda t}^{0} e^{u}\,du = e^{u}\Big|_{-\lambda t}^{0} = e^{0} - e^{-\lambda t} = 1 - e^{-\lambda t}. \quad \square
\end{aligned}
$$

**Ejercicio: Verificar que $P(t)$ es una PDF**, i.e. que $\displaystyle\int_{-\infty}^{\infty} P(t)\,dt = 1$ y que $P(t) \geq 0\ \forall t$.

Si $t < 0$, entonces $P(t) = 0 \Rightarrow P(t) \geq 0$. Si $t \geq 0$, entonces $e^{-\lambda t} > 0$, por lo que $\lambda e^{-\lambda t} \geq 0$ si $\lambda \geq 0$.

Ahora, la integral:
$$
\begin{aligned}
\int_{-\infty}^{\infty} P(t)\,dt
  &= \int_{-\infty}^{0} P(t)\,dt + \int_{0}^{\infty} P(t)\,dt \\
  &= \lim_{b\to\infty}\int_{0}^{b} \lambda e^{-\lambda t}\,dt
   = \lim_{b\to\infty} \left[-e^{-\lambda t}\right]_{0}^{b} \\
  &= e^{-\lambda(0)} - \lim_{b\to\infty} \frac{1}{e^{\lambda b}}
   = 1 - 0 = 1. \quad \square
\end{aligned}
$$

### Ejemplo: Bombilla

Suponga que el tiempo de vida de una bombilla es 100 hrs (promedio). ¿Cuál es la probabilidad de que una bombilla aleatoria dure al menos 50 hrs?

$$
\lambda = \frac{1}{100}, \qquad
P(T \geq 50) = 1 - P(T < 50) = 1 - (1 - e^{-\lambda t}) = e^{-\lambda t} = e^{-\frac{1}{100}\cdot 50} = e^{-1/2} \approx 0.6065.
$$

### Ejemplo: Vida media / semi-vida del plutonio

La vida media/semi-vida del plutonio 210 es 138 días. La vida media es el valor $t$ tal que $P(\text{hasta } t) = 50\% = \frac{1}{2}$, es decir $F(t) = \frac{1}{2}$, donde $F(t) = \text{CDF}$.

$$
F(138) = \frac{1}{2} \implies 1 - e^{-\lambda(138)} = \frac{1}{2} \implies \frac{1}{2} = e^{-\lambda(138)}
\implies \ln\!\left(\frac{1}{2}\right) = -138\lambda
\implies \lambda = \frac{\ln(1/2)}{-138} = \frac{\ln 2}{138}.
$$

## Propiedad "Sin Memoria" (*Memoryless*)

Dada $T \sim \text{exponencial}(\lambda)$, tenemos que:
$$
P(T > t+s \mid T > s) = P(T > t).
$$
Si ya pasó un tiempo $s$, la prob. de "durar" otro tiempo $t$ es la misma que la de durar $t$ desde el inicio.

### Ejemplo: Tasa de Riesgo

¿Cuál es la probabilidad $P(t \leq T \leq t + dt \mid T > t)$?

Esta probabilidad es lo mismo que $1 - P(T > t+dt \mid T > t)$, que por la propiedad "sin memoria" es:
$$
1 - P(T > dt) = 1 - e^{-\lambda\,dt}
= 1 - \underbrace{\left[1 - \lambda\,dt + \frac{1}{2}\lambda^2 dt^2 - \cdots\right]}_{\text{Serie de Taylor}}
\approx \lambda\,dt \quad \to \text{tasa de riesgo.}
$$

$$
\Rightarrow P(t \leq T \leq t+dt) = \lambda\,P(T > t)\,dt.
$$
### Distribución Exponencial & Procesos Poisson

Tenemos una lista de eventos, como emails, tal que:

1. Los tiempos de espera $w_j$ son independientes, y
   $$ w_j \sim \text{exponencial}(\lambda), \qquad \lambda = \text{tasa de eventos} \;(\lambda = \#\text{ eventos/min}). $$

2. El número de eventos en un intervalo $t$ sigue una distribución $\text{Poisson}(\lambda t)$.

**Ejemplo:** Emails llegan cada 5 minutos, i.e., $\lambda = 5$. La probabilidad de esperar $t$ min para el siguiente email es

$$ P(T > t) = e^{-5t} \quad \bigl(= 1 - P(T \leq t) = 1 - (1 - e^{-\lambda t})\bigr). $$

¿Cuál es la probabilidad de no recibir emails en los siguientes $t$ minutos?  
Este es un proceso Poisson, donde tenemos:

$$ P(K = 0 \text{ en } t \text{ min}) = \frac{\lambda^0\, e^{-\lambda t}}{0!} = e^{-5t}. $$

El ejemplo sirve para mostrar la relación entre eventos exponenciales y Poisson.