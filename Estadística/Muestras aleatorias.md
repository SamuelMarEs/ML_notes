Dada una **población** grande $\{x_1, ... ,x_N\}$, vamos a crear una **muestra** $\{X_1, ..., X_n\}$, que es un subconjunto de la población, de tamaño $n$. Cada una de estas muestras es una [[Variable aleatoria]]. 
La idea de la estadística es preguntarnos, ¿podemos inferir algo sobre la **población** en base a la **muestra aleatoria**?

Para la **población** tenemos las siguientes "estadísticas":
$$\mu = \frac{1}{N}\sum_{i=1}^{N}x_i \quad\text{y}\quad \sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2.$$

De la misma forma tenemos las estadísticas equivalentes para la **muestra**:
$$\bar{X}=\frac{1}{n}\sum_{i=1}^{n}X_i \quad\text{y}\quad \hat{\sigma}^2==\frac{1}{n}\sum_{i=1}^{n}(X_i-\bar{X})^2,$$
que son la media muestral y la varianza muestral.

En total hay $\binom{N}{n}$ muestras aleatorias posibles, todas equiprobables. Esto se llama **muestreo aleatorio simple**. 