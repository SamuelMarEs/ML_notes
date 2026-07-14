Una distribución o [[Variable aleatoria]] Gamma representa la probabilidad de que se produzca un tiempo de espera $t$ para el $r$-ésimo evento:

$$ T_r = w_1 + w_2 + \cdots + w_r, \qquad T_r \sim \text{gamma}(r, \lambda). $$

$$ \underbrace{P(T_r > t)}_{\text{gamma}} = \underbrace{P(N_t \leq r-1)}_{\text{Poisson}}. $$

Está estrechamente relacionada con la [[Distribución Poisson]]. La probabilidad Poisson en este caso se refiere a la probabilidad de tener menos de $r$ eventos en el tiempo $t$. $T_r$ significa que el tiempo para el evento $r$ sea mayor a $t$.

$$ P(N_t \leq r-1) = \sum_{k=0}^{r-1} \frac{e^{-\lambda t}(\lambda t)^k}{k!} \quad \leftarrow \text{Esta es una CDF.} $$

$$ \boxed{f(t) = e^{-\lambda t}\,\frac{\lambda^r\, t^{r-1}}{(r-1)!}} \quad \longrightarrow \text{PDF de la distribución gamma.} $$

### Ejemplo: Cola para trámite

Suponga que estamos en la cola para realizar un trámite. Digamos que hay 3 filas, cada una distribuida exponencialmente, con un tiempo de espera de 15 min.

Entonces $\lambda = \dfrac{1}{15}$. Al ser 3 filas, pasa a ser una distribución gamma, donde tenemos que pasar por las 3 filas, cada una con tiempo de espera 15 min.

Es decir que

$$ T_r \sim \text{gamma}\!\left(3,\; \frac{1}{15}\right), $$

donde $r = 3$ y $\lambda = \dfrac{1}{15}$.