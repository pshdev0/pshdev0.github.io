## Appendix A
Let $\pi(x)$ be the prime counting function, i.e. the number of primes less than or equal to $x$, so, for example, $\pi(2)=|\{2,3,5,7,11,13,17,19\}|=8$. Euclid proved there are an infinite number of primes by supposing that $p_1,p_2,\ldots,p_N$ to be prime, and letting $z=p_1p_2\cdots p_N+1$. None of the $p_{i\leq N}$ divide $z$ since we always have a remainder of $1$. This implies that either $z$ is prime, or that $z$ is composite (using some as yet undiscovered prime)

**Theorem.** 
  If $a^n-1$ is prime, then $a=2$ and $n$ is prime.

**Proof.**
Consider the identity
$$x^{km}-1\equiv(x^k-1)(1+x^k+x^{2k}+\cdots+x^{k(m-1)}),\tag{1}$$
which can be easily verified by expanding the bracket and simplifying. Let $n=km$, which is by definition composite. Then by identity (1) we see that $x^k-1\mid x^n-1$, from which we deduce that if $n$ is composite, so is $x^n-1$. Now suppose that $x^n-1$ is not composite, i.e. suppose it to be prime, then $x^k-1\mid x^n-1$ implies $x^k-1=1$ since only 1 and $x^n-1$ divide $x^n-1$. Therefore $x^k=2$ which implies $x=2$.

## Appendix B
The factorial function is defined over $\mathbb{N}$ by
$$
  f(n) = n! = \left\{\begin{array}{ll} n(n-1)(n-2)\cdots 3\cdot 2\cdot 1 & n>0\\
		      1& n=0
                     \end{array}\right..
$$
We would like to extend this over $\mathbb{C}$. Define
$$
  \phi(s) = \prod_{j\geq 1}\left(1+\frac{s}{j}\right)e^{-s/j},
$$
which is an entire function with simple zeros at $s=-1,-2,-3,\ldots$. Now let $\psi_1(s)=s\phi(s)$ and $\psi_2(s)=\phi(s-1)$. The function $\psi_1(s)$ is entire with simple poles at $s=0,-1,-2,-3,\ldots$.
**Theorem.** 
  \label{ref:thm100}
  There exists a constant $\gamma$ such that $\phi(s-1)=e^\gamma s \phi(s)$.

**Proof.**
  The Weierstrass Factorisation theorem says there exists an entire function $F$ such that $\phi(s-1)=e^{F(s)}s\phi(s)$. Taking logarithmic derivatives,
  $$
    \frac{\phi'}{\phi}(s-1)=F'(s)+\frac{1}{s}+\frac{\phi'}{\phi}(s).
  $$
  Therefore
  $$
    F'(s) = \frac{\phi'}{\phi}(s-1)-\frac{\phi'}{\phi}(s)-\frac{1}{s}.
  $$
  But,
  $$
    \frac{\phi'}{\phi}(s) = \frac{d}{ds}\sum_{j\geq 1}\left(\log\left(1+\frac{s}{j}\right)-\frac{s}{j}\right)=\sum_{j\geq 1}\left(\frac{1}{j+s}-\frac{1}{j}\right),
  $$
  and
  $$
    \frac{\phi'}{\phi}(s-1) = \frac{d}{ds}\sum_{j\geq 1}\left(\log\left(1+\frac{s-1}{j}\right)-\frac{s-1}{j}\right) = \sum_{j\geq 1}\left(\frac{1}{j+s-1}-\frac{1}{j}\right).
  $$
  Hence,
  $$
    F'(s) = \sum_{j\geq 1}\left(\frac{1}{j+s-1}-\frac{1}{j+s}\right)-\frac{1}{s} = 0
  $$
  since the sum is a telescoping sum, and since $F'(s)=0$ then $F(s)$ must be constant.
  
  Now, $\phi(0)=1$, and
  $$
    \phi(1) = \prod_{j\geq 1}\left(1+\frac{1}{j}\right)e^{-1/j}=\lim c_n,
  $$
  where $c_n$ is the $n$-th parial product. Taking logarithms,
  $$
    \log c_n = \sum_{j=1}^n\left(\log\left(1+\frac{1}{j}\right)-\frac{1}{j}\right)$$

  $$=-\sum_{j=1}^n\frac{1}{j}+\sum_{j=1}^n\log\left(\frac{j+1}{j}\right)$$
  $$-\sum_{j=1}^n\frac{1}{j}+\log(n+1).$$

  This implies $c_n\longrightarrow e^{-\gamma}$ as $n\longrightarrow\infty$. Hence, as $s\longrightarrow 1$, the expression
  $$
    \phi(s-1)=e^k s \phi(s)
  $$
  becomes
  $$
    1 = e^ke^{-\gamma},
  $$
  which implies $k=\gamma$.
\end{proof}

Now we are ready to define the Gamma function,
$$
  \Gamma(s) = \frac{e^{-\gamma^s}}{s\phi(s)},
$$
which, due to the zeroes of $s\phi(s)$, tells us that $\Gamma(s)$ has simple poles at $0, -1, -2, -3, \ldots$. This implies that $\Gamma(s)$ is meromorphic, and furthermore the numerator tells us the function has no zeroes. Other properties include $\Gamma(1)=e^{-\gamma}/\phi(1) = 1$, since $\phi(1)\longrightarrow e^{-\gamma}$, and that
$$
  \Gamma(s+1)=s\Gamma(s).
$$
This holds if and only if we have
$$
  \frac{e^{-\gamma^{s+1}}}{(s+1)\phi(s+1)} = \frac{se^{-\gamma^s}}{s\phi(s)},
$$
which in turn is true if and only if
$$
  e^{-\gamma}\phi(s)=(s+1)\phi(s+1),
$$
which is true by Theorem \ref{ref:thm100}. Consequently, suppose $n\in\mathbb{N}$. Then we have
$$
  \gamma(n+1)=n\Gamma(n) = n(n-1)\cdots 3\cdot 2\cdot 1 = n!,
$$
so we have
$$
  \Gamma(n+1)=n!,
$$
for $n\in\mathbb{N}$. Hence $\Gamma(s)$ extends $n!$ all over $\mathbb{C}$.
## Appendix C
**Theorem.** 
  $$
    \sum_{k=2}^\infty\frac{\zeta(k)-1}{k} = 1-\gamma.
  $$

**Proof.**
$$\gamma = \lim_{n\to\infty}\left(\sum_{k=1}^n\frac{1}{k}-\log n\right) = \lim_{n\to\infty}\left(\sum_{k=1}^n\frac{1}{k}-\sum_{k=2}^n\log\left(\frac{k}{k-1}\right)\right)$$
$$=\lim_{n\to\infty} 1+\sum_{k=2}^n\left(\frac{1}{k}+\log\left(\frac{k-1}{k}\right)\right)$$
$$=1+\sum_{k=2}^\infty\left(1\frac{1}{k}+\log\left(1-\frac{1}{k}\right)\right)$$
$$=1+\sum_{k=2}^\infty\left(\frac{1}{k}-\sum_{j=1}^\infty\frac{1}{jk^k}\right)$$
$$=1+\sum_{k=2}^\infty\sum_{j=2}^\infty\left(-\frac{1}{jk^j}\right)=1-\sum_{k=2}^\infty\sum_{j=2}^\infty\frac{1}{jk^j}$$
$$=1-\sum_{j=2}^\infty\frac{1}{j}\sum_{k=2}^\infty\frac{1}{k^j} = 1-\sum_{j=2}^\infty\frac{1}{j}(\zeta(j)-1).$$

## Appendix D
## Appendix G
A simple ``proof'' of Euler's Product for $\zeta(s)$.
**Proof.**
$$\prod_p(1-p^{-s})^{-1} = (1-2^{-s})^{-1}(1-3^{-s})^{-1}(1-5^{-s})^{-1}(1-7^{-s})^{-1}\cdots$$
$$=\frac{1}{1-2^{-s}}\frac{1}{1-3^{-s}}\frac{1}{1-5^{-s}}\frac{1}{1-7^{-s}}\cdots$$
$$=(1+2^{-s}+2^{-2s}+2^{-3s}+2^{-4s}+\cdots)\times$$
$$(1+3^{-s}+3^{-2s}+3^{-3s}+3^{-4s}+\cdots)\times$$
$$(1+5^{-s}+5^{-2s}+5^{-3s}+5^{-4s}+\cdots)\times$$
$$(1+7^{-s}+7^{-2s}+7^{-3s}+7^{-4s}+\cdots)\times$$
$$\quad\quad\quad\quad\quad\quad\quad\quad\vdots$$
$$(1+p^{-s}+p^{-2s}+p^{-3s}+p^{-4s}+\cdots)\times$$
$$\quad\quad\quad\quad\quad\quad\quad\quad\vdots$$
$$=1+2^{-s}+3^{-s}+4^{-s}+\cdots\quad\quad\quad\quad(\text{by unique factorisation of }\mathbb{N})$$
$$=\zeta(s).$$
## Appendix H
Concerning Riemann explicit formula. Applying the Mellin transform to the left we see that
$$J(x)=\frac{1}{2\pi i}\int_{a-i\infty}^{a+i\infty}\frac{\log\zeta(s)}{s}x^sdx,a>1.$$
Using IBP,
$$\left.\frac{1}{2\pi i\log x}\log\zeta(s)\frac{x^s}{s}\right|_{a-i\infty}^{a+i\infty}-\frac{1}{2\pi i}\int_{a-i\infty}^{a+i\infty}\left(\frac{\log\zeta(s)}{s}\right)'\frac{x^sds}{\log x}.$$
Turns out the left hand term goes to zero since
$$\left|\log\zeta(a+i T)\right|=\left|\sum_n\sum_p\frac{1}{n}\frac{1}{p^{n(a+iT)}}\right|\leq\sum\sum\frac{1}{n}p^{-na}=\log\zeta(a).$$
$$\log\zeta(s)=\log\prod(1-p^{-s})^{-1}=-\sum\log(1-p^{-s})=\sum\sum\frac{p^{-ns}{n}}{n},$$
therefore $$\frac{\log\zeta(a+iT)x^{a\pm iT}}{a+i T}\to 0 as T\to\infty,$$
because
$$\left|\frac{\log\zeta(a+iT)x^{a\pm iT}}{a+iT}\right|\leq\frac{\log\zeta(a)x^a}{\sqrt{a^2+T^2}},$$
therefore IBP gives
$$J(x)=\frac{1}{2\pi i\log x}\int_{a-i\infty}^{a+i\infty}\left(\frac{\log\zeta(s)}{s}\right)'x^sds.$$
Therefore $M^{-1}(\frac{1}{2}\log\pi)=0$.

What about the next term (integrand) ?, i.e. $-\log(s)/s$.

TODO: see the aside about a theorem from complex analysis - think this is just some background on how to compute the Mellin transform.

TODO: there seems to be a little more on the other terms. Add later when I have a better idea of what's going on. Only a couple of pages.

