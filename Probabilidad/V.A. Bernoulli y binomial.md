Una [[Variable aleatoria]] de distribución *Bernoulli* solo puede tomar dos valores.
Rango $= \{0, 1\}$ (cuando *no* sucede / cuando *sí* sucede):
$$
P(X=0) = 1 - p = q \quad \to \text{prob. de que no pase.}
$$
$$
P(X=1) = p \quad \to \text{prob. de que pase.}
$$

Una variable aleatoria de distribución **Binomial** es como "juntar" varias distribuciones Bernoulli.
Si se realizan $n$ intentos $(B_1, \ldots, B_n)$ con distribución Bernoulli, sea $X$ el número total de casos positivos:
$$
X = B_1 + \cdots + B_n, \qquad X \sim \text{binomial}(n, p) \quad \text{(parámetros)}.
$$
Entonces tenemos que:
$$
P(X = k) = \binom{n}{k} p^k\, q^{n-k} = \binom{n}{k} p^k (1-p)^{n-k}.
$$
Probabilidad de obtener $k$ éxitos en $n$ intentos.

**Ejemplo:** $n=2$, con probabilidad $p$. Entonces:
$$
P(X=0) = P(F_1 \cap F_2) = P(F_1)\,P(F_2) = q^2.
$$
$$
\begin{aligned}
P(X=1) &= P(E_1 \cap F_2) + P(F_1 \cap E_2) \\
       &= P(E_1)P(F_2) + P(F_1)P(E_2) = pq + qp = 2pq.
\end{aligned}
$$
$$
P(X=2) = P(E_1 \cap E_2) = P(E_1)\,P(E_2) = p^2.
$$

**Ejemplo:** Calcular la probabilidad de obtener 3 seises al tirar un dado 12 veces.

Tenemos que $n=12$, $k=3$, $p=\tfrac{1}{6}$, $q=(1-p)=\tfrac{5}{6}$. Dado que $X \sim \text{binomial}(n,p)$:
$$
P(X=3) = \binom{n}{k} p^k\, q^{n-k} = \binom{12}{3}\left(\frac{1}{6}\right)^3\!\left(\frac{5}{6}\right)^9 \approx 0.1973.
$$