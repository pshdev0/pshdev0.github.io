# The Von Mangoldt Explicit Formula
**Definition.** 
Let $x\neq p^k$ and define the function
$$
  \psi(x) = \sum_{n\leq x}\Lambda(n)\quad and \quad
  \psi(x) = \frac{\psi(x+0)+\psi(x-0)}{2},
$$
for all $x\geq 2$.


**Theorem.** 
The Von-Mangoldt explicit formula states that
$$
  \psi(x) = x - \sum_{\substack{\zeta(\rho)=0\\0<Re(\rho)<1}}\frac{x^\rho}{\rho}-\frac{1}{2}\log\left(1-\frac{1}{x^2}\right)-\log(2\pi)=x-\sum\frac{x^\rho}{\rho}+O(1).\tag{1}$$

**Proof.** Consider the function $$f(x) = x - \sum_{\substack{\zeta(\rho)=0\\0<Re(\rho)<1}}\frac{x^\rho}{\rho}-\frac{1}{2}\log\left(1-\frac{1}{x^2}\right)-\log(2\pi).$$ Taking the Mellin transform of each term we see that
[\quad\quad\quad1.]
  - $\displaystyle(\mathcal{M}x)(s)=\frac{1}{s-1}$
  - $\displaystyle\left(\mathcal{M}\frac{-x^\rho}{\rho}\right)(s)=-\frac{1}{\rho(s-\rho)}$
  - $\displaystyle\left(\mathcal{M}-\frac{1}{2}\log\left(1-\frac{1}{x^2}\right)\right)(s)=\sum\frac{1}{2n(s+2n)}$
  - $\displaystyle(\mathcal{M}-\log(2\pi))(s)=-\frac{\log(2\pi)}{s}$,

and so $$-s(\mathcal{M}f)(s) = \frac{s}{1-s}+\sum_{complex s}\frac{s}{\rho(s-\rho)}+\sum_{n\geq 1}\frac{-s}{2n(s+2n)}+\log(2\pi).$$
This expression is equivalent to the logarithmic derivative of the Hadamard product,
$$\frac{d}{ds}\log\left(\frac{1}{2}\left(\frac{2\pi}{\tau}\right)^s\prod_{\zeta(\rho)=0}\left(1-\frac{s}{\rho}\right)e^{s/\rho}\right)=\frac{d}{ds}\log\zeta(s)=\frac{\zeta'(s)}{\zeta(s)},$$
But $$\frac{\zeta'(s)}{\zeta(s)} = -\sum_{n\geq 1}\frac{\Lambda(n)}{n^s}=-\sum_{n\geq 1}\frac{\psi(n+1)-\psi(n)}{n^s},$$
which can be rewritten as a telescoping sum,

$$-\sum_{n\geq 1}\psi(n)\left(\frac{1}{n^s}-\frac{1}{(n+1)^s}\right)=-s\sum\int_{n}^{n+1}\psi(n)x^{-s-1}dx=-s\int_{1}^{\infty}\psi(x)x^{-s-1}dx.$$

Hence, $$ -s(\mathcal{M}f)(s) = -s(\mathcal{M}\psi(x))(s),$$ and so by the injectivity property of the Mellin transform it must be that $\psi(x)=f(x)$, as required.

The left hand side in equation (1) depends only on the primes and the right hand side only on the non-trivial Riemann zeros, so although the primes and the Riemann zeros seem unrelated, the above relationship tells us this is not so.
