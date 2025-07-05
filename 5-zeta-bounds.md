# Upper \& Lower Bounds of $\zeta(s)$
**Theorem.** 
Let $\sigma>1$, then
$$\frac{1}{\sigma-1}\leq\zeta(\sigma)\leq\frac{1}{\sigma-1}+1=\frac{\sigma}{\sigma-1}.$$

**Proof.** TODO

**Theorem.** 
When $\sigma\geq 1$ and $t\geq 2$, then
$$|\zeta(\sigma+it)|\leq\log t+\frac{7}{2}.$$

**Proof.**
Let $N=[t]\geq 2$, then $N\leq t<N+1$. By theorem (reference ?),
$$\zeta(s)=\sum_{n=1}^N\frac{1}{n^s}-\frac{N^{1-s}}{1-s}+R_N(s).$$
Consider the first term,
$$\left|\sum_{n=1}^N\frac{1}{n^s}\right|\leq\sum_{n=1}^N\left|\frac{1}{n^s}\right|=\sum_{n=1}^N\frac{1}{n^\sigma}.$$
But this is equivalent to 
$$1+\sum_{n=2}^N\frac{1}{n}\leq 1+\sum_{n=2}^N\int_{n-1}^n\frac{dt}{t}=1+\int_1^N\frac{dt}{t}=1+\log N\leq 1+\log t.$$
For the second term,
$$\left|\frac{N^{1-s}}{s-1}\right|=\frac{N^{1-\sigma}}{|\sigma-1+it|}\leq\frac{1}{|t|}\leq\frac{1}{2},$$
since $N^{1-\sigma}<0$ and $t\geq 2$.
For the error term,
$$|R_N(s)|\leq\frac{|s|}{\sigma N^\sigma}=\frac{|\sigma+it|}{\sigma N^\sigma}=\frac{|1+it/\sigma|}{N^\sigma}\leq\frac{1+t/\sigma}{N^\sigma}\leq\frac{1+t}{N}\leq\frac{1+N+1}{N}=\frac{2}{N}+1\leq 2.$$
Adding these three estimates together gives the result.

**Theorem.** 
When $\sigma\geq 1$ and $t\geq 2$, then
$$|\zeta'(\sigma+it)|\leq\left(\log t+\frac{7}{4}\right)^2.$$

**Proof.** TODO

**Theorem.** 
When $\sigma\geq 1$ and $t\geq 2$, then
$$|\zeta'(\sigma+it)|\leq\left(\log t+\frac{7}{2}\right)^2.$$

**Proof.** TODO

**Theorem.** 
When $\sigma\geq 1$ and $t\geq 2$, then
$$|\zeta(\sigma+it)|\geq\frac{1}{2^5\left(\log t+5\right)^7}.$$

**Proof.**
By theorem (reference ?),
$$|\zeta^3(\sigma)\zeta^4(\sigma+it)\zeta(\sigma+2it)|\geq 1,$$
which we can rearrange to obtain
$$|\zeta(\sigma+it)|\geq\left(\frac{1}{\zeta^3(\sigma)\zeta(\sigma+2it)}\right)^{1/4}\geq\frac{(\sigma-1)^{3/4}}{\sigma^{3/4}\left(\log(2t)+\frac{7}{4}\right)^2}.$$
by theorems\footnote{ref the two above theorems !}, which is valid for $\sigma\geq\sigma_t$, where \color{red}$\sigma_t$ is to be determined\color{black}.
 For the case $1\leq\sigma<\sigma_t$, let $z=\zeta(\sigma+it)$ and $w=\zeta(\sigma_t+it)$, then $$|z-w|=\left|\int_{\sigma_t}^\sigma\zeta'(y+it)dy\right|\leq \color{red}c\color{black}|w|,$$
by theorem (ref theorem above.). Using the reverse triangle inequality,
$$|z|=|w+(z-w)|\geq|w|-|z-w|\geq|w|-c|w|=(1-c)|w|.$$
