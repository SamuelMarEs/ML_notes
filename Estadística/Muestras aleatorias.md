Dada una **población** grande $\{x_1, ... ,x_N\}$ con media $\mu$ y varianza $\sigma^2$, vamos a crear una **muestra** $\{X_1, ..., X_n\}$, que es un subconjunto de la población, de tamaño $n$. Cada una de estas muestras es una [[Variable aleatoria]]. 
La idea de la estadística es preguntarnos, ¿podemos inferir algo sobre la **población** en base a la **muestra aleatoria**?

Para la **población** tenemos las siguientes "estadísticas":
$$\mu = \frac{1}{N}\sum_{i=1}^{N}x_i \quad\text{y}\quad \sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2.$$

De la misma forma tenemos las estadísticas equivalentes para la **muestra**:
$$\bar{X}=\frac{1}{n}\sum_{i=1}^{n}X_i \quad\text{y}\quad \hat{\sigma}^2=\frac{1}{n}\sum_{i=1}^{n}(X_i-\bar{X})^2,$$
que son la media muestral y la varianza muestral.
En general, la media y la varianza de la población no se pueden calcular, pero se pueden aproximar utilizando la media muestral y la varianza muestral.

En total hay $\binom{N}{n}$ muestras aleatorias posibles, todas equiprobables. Esto se llama **muestreo aleatorio simple**. 

Se puede mostrar que $E(\bar{X})=\mu$.  
Sabemos que 
$$E(\bar{X})=E\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)=\frac{1}{n}\sum_{i=1}^{n}E(X_i).$$
Tomemos en cuenta que $E(X_i)=\mu$ y $Var(X_i)=\sigma^2$  para todos los $X_i$. Por lo tanto se sigue de forma inmediata que 
$$E(\bar{X})=\mu.\quad\square$$
¿Y que hay de la varianza de esta media muestral? Es decir, que sucede con $Var(\bar{X})$. Si asumimos que todas las muestras $X_i$ son independientes entre sí, tenemos
$$Var(\bar{X})=Var\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)=\frac{1}{n^2}\sum_{i=1}^{n}Var(X_i),$$
de lo cuál se sigue inmediatamente que 
$$Var(\bar{X})=\frac{\sigma^2}{n}.$$
De forma más general, es decir sin asumir independencia entre las muestras, se tiene que
$$Var(\bar{X})=\frac{\sigma^2}{n}\left[1-\frac{n-1}{N-1}\right].$$
Para mostrar esto primero tenemos que enunciar el siguiente lema:
**Lema:** $Cov(X_i, X_j)=-\frac{\sigma^2}{N-1}$ si $i\neq j$.
Entonces, tenemos que:
$$\begin{align}
Var(\bar{X})&=Cov(\bar{X},\bar{X}) \\
			&=Cov\left(\frac{1}{n}\sum_{i=1}^{n}X_i, \frac{1}{n}\sum_{j=1}^{n}X_j\right) \\
			&=\frac{1}{n^2}\sum_{i=1}^{n}\sum_{j=1}^{n}Cov(X_i,X_j) \\
			&=\frac{1}{n^2}\left[\sum_{i=j}Cov(X_i,X_j)+\sum_{i\neq j}Cov(X_i,Xj)\right]  \\
			&=\frac{1}{n^2}\left[n\sigma^2+n(n-1)\left(-\frac{\sigma^2}{(N-1)}\right)\right] \\
			&=\frac{\sigma^2}{n}\left[1-\frac{n-1}{N-1}\right].\quad\square
\end{align}$$

Ahora vamos a trabajar con la varianza muestral. En particular, ¿qué sucede si calculamos su valor esperado? Es decir:
$$\begin{align}
E(\hat{\sigma}^{2})&=\frac{1}{n}\sum_{i=1}^{n}E[X_{i}^{2}-\bar{X}^{2}]  \\
 & = \frac{1}{n}\sum_{i=1}^{n}[(Var(X_{i})+E(X_{i})^{2})-(Var(\bar{X})+E(\bar{X})^{2})]  \\
 & = \frac{1}{n}\sum_{i=1}^{n}\left[ \sigma^{2}-\frac{\sigma rs}{n}\left( 1-\frac{n-1}{N-1} \right) \right] \\
 & =\frac{\sigma^{2}}{n} \frac{N(n-1)}{N-1}.
\end{align}$$
Entonces tenemos que 
$$
	E\left( \frac{n(N-1)}{N(n-1)} \hat{\sigma}^{2} \right) = \sigma^{2}.
$$
