Dada una **población** grande $\{x_1, ... ,x_N\}$, vamos a crear una **muestra** $\{X_1, ..., X_n\}$, que es un subconjunto de la población, de tamaño $n$. Cada una de estas muestras es una [[Variable aleatoria]]. 
La idea de la estadística es preguntarnos, ¿podemos inferir algo sobre la **población** en base a la **muestra aleatoria**?

Para la **población** tenemos las siguientes "estadísticas":
$$\mu = \frac{1}{N}\sum_{i=1}^{N}x_i \quad\text{y}\quad \sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2.$$

De la misma forma tenemos las estadísticas equivalentes para la **muestra**:
$$\bar{X}=\frac{1}{n}\sum_{i=1}^{n}X_i \quad\text{y}\quad \hat{\sigma}^2=\frac{1}{n}\sum_{i=1}^{n}(X_i-\bar{X})^2,$$
que son la media muestral y la varianza muestral.

En total hay $\binom{N}{n}$ muestras aleatorias posibles, todas equiprobables. Esto se llama **muestreo aleatorio simple**. 

Se puede mostrar que $E(\bar{X})=\mu$.  
Sabemos que 
$$E(\bar{X})=E(\frac{1}{n}\sum_{i=1}^{n}X_i)=\frac{1}{n}\sum_{i=1}^{n}E(X_i).$$
Tomemos en cuenta que $E(X_i)=\mu$ y $Var(X_i)=\sigma^2$  para todos los $X_i$. Por lo tanto se sigue de forma inmediata que 
$$E(\bar{X})=\mu.\quad\square$$
¿Y que hay de la varianza de esta media muestral? Es decir, que sucede con $Var(\bar{X})$. Si asumimos que todas las muestras $X_i$ son independientes entre sí, tenemos
$$Var(\bar{X})=Var(\frac{1}{n}\sum_{i=1}^{n}X_i)=\frac{1}{n^2}\sum_{i=1}^{n}Var(X_i),$$
de lo cuál se sigue inmediatamente que 
$$Var(\bar{X})=\frac{\sigma^2}{n}.$$

