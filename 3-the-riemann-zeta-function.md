# The Riemann Zeta Function

Define
$$
  \zeta(s)=\sum_{n\geq 1}\frac{1}{n^s} = 1+\frac{1}{2^s}+\frac{1}{3^s}\cdots.
$$
**Theorem.** 
  The series $\zeta(s)$ (i) converges for $s>1$,
(ii) diverges for $s\leq 1$, and (iii) for $s>1$ we have
$$1\leq\zeta(s)\leq\frac{1}{1-2^{1-s}},$$
so that $\zeta(s)\rightarrow 1$ as $s\rightarrow\infty$.

**Proof.**
  (i) Let $s>1$, then
  $$\sum_{n\geq 1}\frac{1}{n^s}=\sum_{k=0}^\infty\sum_{m=2^k}^{2^{k+1}-1}\frac{1}{m^s}<\sum_{k=0}^\infty\sum_{m=2^k}^{2^{k+1}-1}\frac{1}{\left(2^k\right)^s}=\sum_{k=0}^\infty(2^k)^{-s}\sum_{m=2^k}^{2^{k+1}-1}1.$$
But
$$\sum_{m=2^k}^{2^{k+1}-1}1=2^{k+1}-1-(2^k-1)=2^{k+1}-2^k=2^k,$$
so we have
$$\sum_{k=0}^\infty(2^k)^{1-s}=\sum_{k=0}^\infty(2^{1-s})^k=\frac{1}{1-2^{1-s}}<\infty,$$
since $0<2^{1-s}<1$.

  (ii)   Let $0<s\leq 1$, then
  $$\sum_{n=1}^\infty\frac{1}{n^s}=1+\sum_{k=0}^\infty\sum_{m=2^k+1}^{2^{k+1}}\frac{1}{m^s}>1+\sum_{k=0}^\infty\sum_{m=2^k+1}^{2^{k+1}}\frac{1}{2^{k+1}}=1+\sum_{k=0}^\infty\frac{1}{2}\sum_{m=2^k+1}^{2^{k+1}}\frac{1}{2^k}.$$
But,
$$\sum_{m=2^k+1}^{2^{k+1}}\frac{1}{2^k}=\frac{1}{2^k}(2^{k+1}-2^k)=1,$$
so we obtain
$$1+\sum_{k=0}^\infty\frac{1}{2}=\infty.$$
Let $s=-s'$, where $s'>0$, then $n^{-s}=n^{s'}\to\infty$ as $n\to\infty$.

  (iii) Since $1/n^s\to 0$ from above as $s\to\infty$ then a lower bound on $\zeta(s)$ is $1\leq\zeta(s)$. Combined with (*) above we obtain
$$1\leq\zeta(s)\leq\frac{1}{1-2^{1-s}}.$$
But as $s\to\infty$ the right hand side tends to $1$ from above, so by the squeeze theorem we have $\zeta(s)=1$ as $s\to\infty$.

**Proposition.** 
Let $s\in\mathbb{C}$, then $\zeta(s)$ may be split into real and imaginary parts,
$$\zeta(s) = \sum_{n\geq 1}\frac{\cos(t\log n)}{n^\sigma}+i\sum_{n\geq 1}\frac{\sin(t\log n)}{n^\sigma}.$$

**Proof.**
Writing $s=\sigma+it$ then
$$n^{-s}=e^{-s\log n}=e^{-(\sigma+it)\log n}=e^{-\sigma\log n}e^{-it\log n}=\frac{1}{n^\sigma}e^{-it\log n}.$$
Applying Euler's formula $e^{i\theta}=\cos\theta+i\sin\theta$ and summing $n$ over the positive integers gives the result.

**Theorem.** 
  $\zeta(s)$ is holomorphic in $\sigma>1$.

Let $Re(s)=\sigma>1$. Suppose that
$$f(s) = \sum_{n=1}^\infty\frac{1}{n^s}\quad and \quad f_N(s) = \sum_{n=1}^N\frac{1}{n^s},$$
then
  $$\sup_{s\in D}\left|f_N(s)-f(s)\right|=\sup_{s\in D}\left|\sum_{n=N+1}^\infty\frac{1}{n^s}\right|\leq\sup_{s\in D}\sum_{n=N+1}^\infty\frac{1}{n^\sigma}\leq\sum_{n=N+1}^\infty\frac{1}{n^\alpha}\longrightarrow 0,$$
as $N\longrightarrow \infty$, so we have L.U. convergence in $D$. There is no restriction on the disc $D$ since $\alpha$ can be any real value. Now apply the convergence lemma. Since $n^{-s}$ has derivative $-sn^{-s-1}$ then by lemma $\zeta(s)$ is holomorphic in $\sigma>1$.

**Theorem.** [Euler Product]
  $$
    \zeta(s) = \prod_p(1-p^{-s})^{-1}.
  $$

We will use a sieve method. Multiplying
$$  \zeta(s)=1 + \frac{1}{2^s}+\frac{1}{3^s}+\frac{1}{4^s}+\frac{1}{5^s}+\cdots,
$$
by the prime power $2^{-s}$,
$$
  \frac{1}{2^s}\zeta(s) = \frac{1}{2^s}+\frac{1}{4^s}+\frac{1}{6^s}+\frac{1}{8^s}+\frac{1}{10^s}+\cdots,
$$
and subtracting the two, define
$$
  Z_2(s)=\left(1-\frac{1}{2^s}\right)\zeta(s) = 1+\frac{1}{3^s}+\frac{1}{5^s}+\frac{1}{7^2}+\frac{1}{9^s}+\cdots.\tag{1}
$$
Now repeat this process using $Z_2(s)$ and the prime power $3^{-s}$ and define
$$
  Z_3(s)=\left(1-\frac{1}{3^s}\right)\left(1-\frac{1}{2^s}\right)\zeta(s) = 1+\frac{1}{5^s}+\frac{1}{7^s}+\cdots.
$$
We can continue this process with $Z_p(s)$ with $p=3,5,7,11,13,\ldots$
In general,
$$Z_P(s)=\zeta(s)\prod_{p=2}^P\left(1-\frac{1}{p^s}\right)= 1 + \sum_{n\nmid\{2,3,\ldots,p\}}\frac{1}{n^s}.$$
By the right hand side $Z_P(s)\to 1$ as $P\to\infty$ and we have the result. Now, we have
$$
  \left|Z_P(s)-1\right|\leq\sum_{n\geq q}\frac{1}{n^\sigma},\tag{$\dagger$}
$$
where $q$ is the next prime after $P$. We see that
$$
  \sup_{\sigma>1} \left|Z_P(s)-1\right| = \sup_{\sigma>1} \sum_{n\geq q}\frac{1}{n^\sigma}\longrightarrow 0 as P\longrightarrow\infty,
$$
and so we have LU convergence in $\sigma>1$. We conclude that
$Z_P(s) = 1$ as $P\longrightarrow\infty$.
**Theorem.** 
  For $\sigma>1$ then $\zeta(s)\neq 0$.

**Proof.**
By equation ($\dagger$) we have $\left|Z_P(s)-1\right|<\epsilon$ for all $\varepsilon>0$ and $P=P(\varepsilon)$. Let $\zeta(s)=0$ then $1<\epsilon$ which gives a contradiction.
