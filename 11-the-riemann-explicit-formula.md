# The Riemann Explicit Formula
**Definition.** 
Let $x\in\mathbb{R}$ and define the logarithmic integral, $$li(x) = \int_{0}^{x}\frac{1}{\log t}dt.$$ 

**Definition.** 
Define $$J(x) = \sum_{k\geq 1}\frac{1}{k}\pi(x^{1/k}).$$


Note that this is a finite series since for all values of $x$ there exists a $k$ such that $\pi(x^{1/k})=0$. In the sum, the first term is the number of primes $\leq x$, the second term is the number of $p\leq\sqrt{x}$ which corresponds to $p^2\leq x$, the third term corresponds to $p^3\leq x$, and so on.
**Theorem.** 
The Riemann explicit formula states that
$$J(x)=li(x)+\sum li(x^\rho)+\int_x^\infty\frac{1}{t(t^2-1)\log t}dt-\log 2.$$


\begin{proof}
Recall that
$$\frac{\log\zeta(s)}{s}=(\mathcal{M}J)(s)\iff J(y)=\frac{1}{2\pi i}\int_{a-i\infty}^{a+i\infty}\frac{\log\zeta(s)}{s}y^sds.$$
Consider the ``extended'' functional equation,
$$\xi(s)=\frac{s}{2}(s-1)\Gamma(s/2)\pi^{-s/2}\zeta(s),$$
which makes the equation an entire function by removing two singularities. Since $x\Gamma(x)=\Gamma(x+1)$ then
$$\xi(s)=(s-1)\Gamma\left(\frac{s}{2}+1\right)\pi^{-s/2}\zeta(s),$$
from which we get
$$\zeta(s)=\frac{\xi(s)}{(s-1)\Gamma(\frac{s}{2}+1)\pi^{-s/2}}.$$
So,
$$\log\zeta(s)=\log\xi(s)-\log(s-1)-\log\Gamma\left(\frac{s}{2}+1\right)+\frac{s}{2}\log\pi.$$
But, $$\xi(s)=\xi(0)\prod_\rho\left(1-\frac{s}{\rho}\right),$$
so
$$\log\zeta(s)=\log\xi(0)\color{red}+\color{black}\sum_\rho\log\left(1-\frac{s}{\rho}\right)-\log(s-1)-\log\Gamma\left(\frac{s}{2}+1\right)+\frac{s}{2}\log\pi.$$
But
$$\xi(0)=(0-1)\Gamma(1)\zeta(0)=-\zeta(0)=\frac{1}{2},$$
and $\log(1/2)=-\log 2$, so
$$\log\zeta(s)=-\log2+\sum_\rho\log\left(1-\frac{s}{\rho}\right)-\log(s-1)-\log\Gamma\left(\frac{s}{2}+1\right)+\frac{s}{2}\log\pi.$$
Now divide by $s$,
$$\color{red}\frac{\log\zeta(s)}{s}\color{black}=\color{green}-\frac{\log(s-1)}{s}\color{blue}+\frac{\sum\log\left(1-\frac{s}{\rho}\right)}{s}\color{cyan}-\frac{\log\Gamma\left(\frac{s}{2}+1\right)}{s}\color{magenta}-\frac{\log 2}{s}\color{red}+\frac{\frac{s}{2}\log\pi}{s}\color{black},$$
which is the additive version of the product formula. Applying the inverse Mellin transform to each term gives,
$$\color{red}J(x)\color{black}=\color{green}li(x)\color{blue}+\sum li(x^\rho)\color{cyan}+\int_x^\infty\frac{1}{t(t^2-1)\log t}dt\color{magenta}-\log 2\color{red} + 0.$$
Turns out that none of these inverse Mellin transform integrals is easy to perform.
\end{proof}

Similarly to the Von Mangoldt explicit formula, $J(x)$ depends on the primes only, whereas the explicit formula depends only on the non-trivial zeros of $\zeta(s)$. The first two terms in the right hand side are important and the last two terms in the right are less important as they are bounded.

Let us examine the integral term. Let $u=\log t$ so that

$$\int_{\log x}^{\infty}\frac{1}{(e^{2u}-1)u}du = \sum_{n\geq 1}\int_{\log x}^{\infty}\frac{e^{-2nu}}{u}du.$$

Now let $t=e^{-2nu}$, then

$$\sum_{n\geq 1}-\int_{0}^{x^{-2n}}\frac{1}{\log t}dt = -\sum_{n\geq 1}li(x^{-2n}),$$

which involves the trivial zeros only. Hence, we could actually write

$$J(x) = li(x)-\sum_{\zeta(\rho)=0}li(x^\rho)-\log 2,$$

where $\rho$ includes real and complex zeros. Note, however, that

$$\lim_{x\rightarrow\infty} \int_{x}^{\infty}\frac{1}{t(t^2-1)\log t)}dt=0,$$

so the integral vanishes as $x$ increases, and for $x=2$ the integral is approximately $0.14001$.

**Lemma.** 
$$\pi(x) = \sum_{k\geq 1}\frac{\mu(k)}{k}J(x^{1/k}).$$


\begin{proof} We have
    $$\sum_{k\geq 1}\frac{\mu(k)}{k}J(x^{1/k}) = \sum_{k\geq 1}\frac{\mu(k)}{k}\sum_{j\geq 1}\frac{1}{j}\pi(x^{1/(jk)}) = \sum_{j,k\geq 1}\frac{\mu(k)}{kj}\pi(x^{1/(jk)})$$
and then    
	  $$\sum_{d\mid n}\frac{\mu(d)}{n}\pi(x^{1/n})= \mu(1)\pi(x) + \sum_{d\mid n,d>1}\frac{\mu(d)}{n}\pi(x^{1/n})= \pi(x).$$
\end{proof}
We now know that
$$
  \pi(x) = \sum_{n\geq 1}\frac{\mu(n)}{n}J(x^{1/n}),
$$
and
$$
  J(x) = li(x) - \sum li(x^\rho)+O(1).
$$
Combining the two gives a formula for $\pi(x)$ with (i) a bounded term, (ii) an oscillating term, and (iii) an increasing term,
$$\pi(x)=\sum_{n\geq 1}\frac{\mu(n)}{n}\left(li(x^{1/n})-\sum_\rho li(x^{\rho/n})+O(1)\right).$$
But, we can truncate this exact formula to give the so called Riemann Approximation Formula,
  $$
    \pi(x) \approx li(x) + \sum_{n\geq 2}\frac{\mu(n)}{n}li(x^{1/n}).
  $$
This is in fact an improvement on Gauss' earlier discovery that $\pi(x)\approx li(x)$, e.g.
$$
  \begin{array}{lcc}
    x(\times 10^6) & \text{Riemann error} & \text{Gauss error} \\
    1 & 30 & 130\\
    2 & -9 & 122\\
    3 & 0 & 155\\
    4 & 33 & 206\\
    5 & -64 & 125
  \end{array}.
$$
**Definition.** 
Define the logarithmic integral of a complex power $x^{\alpha+i\beta}$, where $\beta\neq 0$ is real and $x>2$ by
$$
  li(x^{\alpha+i\beta}):=\int_{-\infty+i\beta}^{\alpha+i\beta}\frac{x^s}{s}ds.
$$


This definition is compatible with the original since
$$
  li(e^u) = \int_{-\infty}^{u}\frac{e^s}{s}ds = \int_{0}^{e^u}\frac{1}{\log t}dt.
$$
**Theorem.** 
  Let the first zeta zero be $1/2+\gamma_1$, and let $t\geq \gamma_1$. Then
  $$
    \lim_{t\longrightarrow\infty} li(x^{1/2+it})=0,
  $$
  and
  $$
    \lim_{t\longrightarrow-\infty} li(x^{1/2+it})=0.
  $$

> **Note:**  
> The *curves* $t \mapsto \mathrm{li}(x^{1/2 + it})$ and $t \mapsto \mathrm{li}(x^{1/2 - it})$ are spirals centered at zero,  
> each contained in the disc $\{s : |s| \leq x^{1/2}/(\gamma_1 \log x)\}$.

**Proof.**
  Substitute $s=u+it$. Then

$$li(x^{1/2+it}) = \int_{\infty}^{1/2}\frac{x^{u+it}}{u+it}du$$

$$=x^{it}\int_{-\infty}^{1/2}\frac{x^u}{u+it}du.$$

Note - the coefficient of the integral effects the circular motion of the spiral whilst the integral is decreasing. To finish, we have
  $$
    |li(x^{1/2+it})|=\left|\int_{-\infty}^{1/2}\frac{x^u}{u+it}du\right|\leq \frac{1}{t}\int_{-\infty}^{1/2}\frac{x^u}{u}du=\frac{1}{t}\frac{x^{1/2}}{\log x}\leq \frac{1}{\gamma_1}\frac{x^{1/2}}{\log x}.
  $$
  and similarly for $|li(x^{1/2-it})|$.
\end{proof}
Plymen \& Chao (2010) proved that there exists $x<e^{729}$ such that $\pi(x)>li(x)$.
