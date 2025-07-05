# Analytic / Meromorphic Continuation of $\zeta(s)$
**Theorem.** 
  $\zeta(s)$ is meromorphic in $\sigma>0$ with a simple pole at $s=1$, and is given by
  $$
    \zeta(s) = 1 + \frac{1}{s-1}-s\int_{1}^{\infty}\frac{\{x\}}{x^{s+1}}dx.
  $$

**Proof.**
Rewrite the Riemann zeta function,
  $$\zeta(s) = 1-\frac{1}{2^s}+2\left(\frac{1}{2^s}-\frac{1}{3^s}\right)+3\left(\frac{1}{3^s}-\frac{1}{4^s}\right) + \cdots + n\left(\frac{1}{n^s}-\frac{1}{(n+1)^s}\right)+\cdots$$
Using summation notation,
$$\sum_{n\geq 1}n\left(\frac{1}{n^s}-\frac{1}{(n+1)^s}\right)=s\sum_{n\geq 1}n\int_{n}^{n+1}\frac{1}{x^{s+1}}dx=s\sum_{n\geq 1}\int_{n}^{n+1}\frac{[x]}{x^{s+1}}dx=s\int_{1}^{\infty}\frac{[x]}{x^{s+1}}dx,$$
which we can manipulate to give,
$$s\int_{1}^{\infty}\frac{x-\{x\}}{x^{s+1}}dx=s\int_{1}^{\infty}\frac{1}{x^s}dx-s\int_{1}^{\infty}\frac{\{x\}}{x^{s+1}}dx=1+\frac{1}{s-1}-s\int_{1}^{\infty}\frac{\{x\}}{x^{s+1}}dx,$$
which is valid for $\sigma>0$. The integral clearly converges since the shift in $s$ is apparent.
\end{proof}
This description of the Riemann zeta function shows up the singularity, which we did not know before. The singularity is a simple pole at $s=1$.
**Theorem.** 
Let $s=\sigma+it$ with $\sigma>0$ and $\sigma\neq 1$, and let $N\geq 1$ be integers, then
$$\zeta(s)=\sum_{n=1}^N\frac{1}{n^s}-\frac{N^{1-s}}{1-s}+R_N(s),$$
where
$$R_N(s)=-\int_N^\infty\frac{\{u\}}{u^{1+s}}du\quad\text{~and~}\quad|R_N(s)|\leq\frac{|s|}{\sigma N^\sigma}.$$

**Proof.**
Consider the integral
$$-s\int_1^N\frac{\{u\}}{u^{s+1}}du=-s\sum_{n=1}^{N-1}\int_n^{n+1}\frac{u-n}{u^{1+s}}du=-s\sum_{n=1}^{N-1}\int_n^{n+1}\frac{1}{u^s}du+s\sum_{n=1}^{N-1}n\int_n^{n+1}\frac{1}{u^{1+s}},$$
evaluating which gives
$$-\frac{s}{1-s}\sum_{n=1}^{N-1}(1+n)^{1-s}-n^{1-s}+\sum_{n=1}^{N-1}n\left(\frac{1}{n^s}-\frac{1}{(n+1)^s}\right)=-\frac{s}{1-s}\left(N^{1-s}-1\right)+\sum_{n=1}^{N-1}\frac{1}{n^s}-\frac{N-1}{N^s}.$$
Expanding gives,
$$-s\int_1^N\frac{\{u\}}{u^{1+s}}du=\sum_{n=1}^N\frac{1}{n^s}-\frac{N^{1-s}}{1-s}-1+\frac{1}{1-s},$$
Substituting into the previous theorem gives the result. For the inequality,
$$R_N(s)=-s\int_N^\infty\frac{\{u\}}{u^{1+s}}du\leq|s|\int_N^\infty\frac{1}{u^{1+s}}du=\frac{|s|}{\sigma N^\sigma}.$$

**Theorem.** 
  In $0<\sigma<1$ we have
  $$
    \zeta(s) = -s\int_{0}^{\infty}\frac{\{x\}}{x^{s+1}}dx.
  $$


**Proof.**
  Since
  $$
    -s\int_{0}^{1}\frac{\{x\}}{x^{s+1}}dx=-s\int_{0}^{1}\frac{x-[x]}{x^{s+1}}dx=-s\left(-\frac{1}{s-1}\right)=\frac{s}{s-1}=1+\frac{1}{s-1}.
  $$

**Definition.** 
  The Euler constant may be defined:
  $$
    \gamma = \lim_{n\rightarrow\infty} 1+\frac{1}{2}+\frac{1}{3}+\cdots+\frac{1}{N}-\log N \approx 0.577215664925.
  $$

Not a lot is known of $\gamma$. For example, is $\gamma$ rational?

**Theorem.** 
  $$
    \zeta(s) = \frac{1}{s-1}+\gamma+O(s-1).
  $$

**Proof.**
Since $x=[x]+\{x\}$, then
    $$\lim_{s\rightarrow 1}\left(\zeta(s)-\frac{1}{s-1}\right) = 1-\int_{1}^{\infty}\frac{\{x\}}{x^2}dx=1+\lim_{n\rightarrow\infty}\int_{1}^{n}\left(\frac{[x]}{x^2}-\frac{1}{x}\right)dx.$$
	Splitting the integral,
    $$\sum_{m=1}^{n-1}\int_m^{m+1}\frac{m}{x^2}dx-\log n,$$
    so we obtain
    $$1+\lim_{n\to\infty}\sum_{m=1}^{n-1}\frac{1}{m+1}-\log n=\gamma.$$
  The power series in $(s-1)$ disappears since $\lim_{s\rightarrow 1}(s-1)=0$.
**Theorem.** 
  $Re(s)=1$ implies $\zeta(s)\neq 0$.


**Proof. (Hadamard)**
  Suppose $s=\sigma+it$ with $\sigma>1$ then by the Euler product,
  
  $$
    \log\zeta(s) = \sum_p-\log(1-p^{-s}) = \sum_p\sum_{m\geq 1}m^{-1}p^{-ms}=\sum_p\sum_m m^{-1}p^{-m\sigma}e^{itm\log p},
  $$
  from which we obtain
  $$
    Re(\log\zeta(s)) = \sum_p\sum_m m^{-1}p^{-m\sigma}\cos(t\log p^m).\tag{*}
  $$
  Using the following inequality
  $$
  	3+4\cos\theta+\cos(2\theta)=\cos^2\theta-\sin^2\theta+4\cos\theta+3=2\cos^2\theta+4\cos\theta+2=2(\cos\theta+1)^2\geq 0,$$

  substitute $\theta=t\log p^m$ and sum over $p$ and $m$ with kernel $m^{-1}p^{-m\sigma}$ to obtain
  $$
    \sum\sum m^{-1}p^{-m\sigma}(3+4\cos(t\log p^m)+\cos(2t\log p^m))\geq 0.
  $$
  Expanding, and using (*),
  $$
    3Re(\log\zeta(\sigma))+4Re(\log\zeta(\sigma+it))+Re(\log\zeta(\sigma+2it))\geq 0.
  $$
  Since $Re\log z = Re(\log|z|+i\text{Arg} z)=\log|z|$, then
    $$
    \log\zeta(\sigma)^3+\log|\zeta(\sigma+it)|^4+\log|\zeta(\sigma+2it)|\geq 0.
    $$
Exponentiating,
  $$
    \zeta(\sigma)^3|\zeta(\sigma+it)|^4|\zeta(\sigma+2it)|\geq 1,
  $$
  and so multiplying by $1=(\sigma-1)^4/(\sigma-1)^4$,
  $$
    (\sigma-1)^3\zeta^3(\sigma)\left|\frac{\zeta(\sigma+it)}{\sigma-1}\right|^4\left|\zeta(\sigma+2it)\right|(\sigma-1)\geq 1.\tag{*}
  $$
  Now consider
  $$
    \frac{\zeta(\sigma+it)-\zeta(1+it)}{\sigma-1}\longrightarrow\zeta'(1+it)\implies\zeta(\sigma+it)\longrightarrow(\sigma-1)\zeta'(1+it)+\zeta(1+it),
  $$
  as $\sigma\to 1^+$. Substituting into (*),
  $$
    (\sigma-1)^3\zeta(\sigma)^3\left|\zeta'(1+it)+\frac{\zeta(1+it)}{\sigma-1}\right|^4|\zeta(\sigma+2it)|(\sigma-1)\geq 1,
  $$
  as $\sigma\to 1^+$. For a contradiction, suppose $\zeta(1+it)=0$.
Since $(s-1)\zeta(s)=1+\gamma(s-1)+(s-1)O(s-1)$ then $(\sigma-1)^3\zeta^3(\sigma)\longrightarrow 1$, $\zeta(\sigma+2it)\longrightarrow\zeta(1+2it)$, and
  $$
    |\zeta'(1+it)|^4|\zeta(1+2it)|(\sigma-1)\geq 1,
  $$
  but $\sigma-1\longrightarrow 0$, so we obtain $0\geq 1$, which is a contradiction. Hence, we conclude that $\zeta(1+it)\neq 0$.

Using the Wiener–Ikehara theorem (1930, 1951) this theorem can be used to prove the Prime Number Theorem (PNT) - see later.

**Lemma.** 
Let $a\in\mathbb{R}$ and define
$$\psi_a(x)=\sum_{n=a}^\infty e^{-n^2\pi x}.$$
Then
$$\psi_{-\infty}(x)=\frac{\psi_{-\infty}(1/x)}{\sqrt{x}}\quad\text{~and~}\quad\psi_{-\infty}(x)=2\psi_1(x)+1$$
imply
$$\psi_1(x)=\frac{1}{\sqrt{x}}\left(\psi_1(1/x)+\frac{1}{2}\right)-\frac{1}{2}.$$


**Theorem.** [The
 Functional Equation]
Consider the function
$$\xi(s)\equiv\pi^{-s/2}\Gamma(s/2)\zeta(s),$$
where $\Gamma(x)$ is the gamma function which is entire, then $\xi(s)=\xi(1-s)$. 

**Proof. (Titchmarsh, 1986)**
By lemma, summing over all positive integers $n$, then for $\sigma>1$,
$$\frac{\Gamma(s/2)\zeta(s)}{\pi^{s/2}}=\sum_{n=1}^\infty\int_0^\infty x^{s/2-1}e^{-n^2\pi x}dx=\int_0^\infty x^{s/2-1}\psi_1(x)dx,\tag{$\dagger$}$$
where we swapped integral and sum by virtue of absolute convergence. Splitting the integral over $(0,1]\cup[1,\infty)$ and substituting the second lemma gives
$$\int_0^1 x^{s/2-1}\left(\frac{1}{\sqrt{x}}\left(\psi_1(1/x)+\frac{1}{2}\right)-\frac{1}{2}\right)dx+\int_1^\infty x^{s/2-1}\psi_1(x)dx.\tag{$\star$}$$
Expanding the first integral gives

$$\int_0^1 x^{s/2-3/2}\psi_1(1/x)dx+\frac{1}{2}\int_0^1 x^{s/2-3/2}dx-\frac{1}{2}\int_0^1 x^{s/2-1}dx=\int_0^1 x^{s/2-3/2}\psi_1(1/x)dx+\frac{1}{s(s-1)}.$$
Now using the change of variable $x=1/y$ where $dx=-1/y^2dy$,
$$-\int_\infty^1 y^{-s/2+3/2}\psi_1(y
)\frac{dy}{y^2}+\frac{1}{s(s-1)}\equiv\int_1^\infty x^{-s/2-1/2}\psi_1(x
)dx+\frac{1}{s(s-1)}.$$
Substituting back into ($\star$) gives

$$\pi^{-s/2}\Gamma(s/2)\zeta(s)=\frac{1}{s(s-1)}+\int_1^\infty \left(x^{-s/2-1/2}+x^{s/2-1}\right)\psi_1(x)dx,$$

which converges for all $s$, thereby so does the LHS by analytic continuation. Now, if we replace $s$ by $1-s$ in the RHS, then (i) $(1-s)(1-s-1)=(1-s)(-s)=s(s-1)$, (ii) $-(1-s)/2-1/2=s/2-1$ and (iii) $(1-s)/2-1=-s/2-1/2$, which leaves the RHS unchanged. Therefore,

$$\pi^{-s/2}\Gamma(s/2)\zeta(s)=\pi^{-(1-s)/2}\Gamma((1-s)/2)\zeta(1-s),$$

which is the functional equation $\xi(s)=\xi(1-s)$.
\end{proof}
\begin{corollary}
$$\zeta(s)=2^s\pi^{s-1}\sin\left(\frac{\pi s}{2}\right)\Gamma(1-s)\zeta(1-s).$$
\end{corollary}
\begin{proof}
Rearranging the functional equation,
$$\zeta(s)=\pi^{s-1/2}\frac{\Gamma(1/2-s/2)}{\Gamma(s/2)}\zeta(1-s),$$
and applying Legendre's duplication formula,
$$\pi^{s-1/2}\frac{2^{1+s}\pi^{1/2}\Gamma(-s)}{\Gamma(-s/2)\Gamma(s/2)}\zeta(1-s).$$
Using the factorial property,

$$\zeta(s)=\pi^{s-1/2}\frac{-s/2}{-s/2}\frac{2^{1+s}\pi^{1/2}\Gamma(-s)}{\Gamma(-s/2)\Gamma(s/2)}\zeta(1-s)=\pi^{s-1/2}\frac{1}{2}\frac{2^{1+s}\pi^{1/2}\Gamma(1-s)}{\Gamma(1-s/2)\Gamma(s/2)}\zeta(1-s)$$

Finally, applying Euler's reflection formula then gives the result.

**Corollary.**
Let's call the region of the complex plane between $0<\sigma<1$ the "critical strip". Since we know that $\zeta(s)=\zeta(\sigma+it)$ is zero-free for $\sigma\geq 1$ (i.e. $\zeta(s)$ is zero-free to the right of the critical strip), then by the functional equation we know that $\zeta(1-s)=\zeta(1-\sigma-it)$ is zero free, except for at the negative even integers due to the $\sin(\pi s/2)$ term (i.e. $\zeta(s)$ is zero-free to the left of the critical strip except at the negative even integers). These zeros are called the "trivial" zeros of $\zeta(s)$. All other zeros, which we now know must lie inside the critical strip, are called the "non-trivial" zeros.

**Hypothesis. (The Riemann Hypothesis)**
	All non-trivial zeros of $\zeta(s)$ lie on $\sigma=1/2$.

An entire function $f$ is said to be of finite order if there exists $a,r>0$ such that $|f(z)|\leq e^{|z|^a}$ for all $|z|>r$. The \emph{function order} of $f$ is the infimum of all such $a$.

See: https://mathworld.wolfram.com/HadamardFactorizationTheorem.html

**Proposition.** 
Let $\tau$ be some function of $s$, then the Hadamard product representation of the Riemann zeta function is defined by
$$\zeta(s) = \frac{1}{2}\left(\frac{2\pi}{\tau}\right)^s\prod_{\zeta(\rho)=0}\left(1-\frac{s}{\rho}\right)e^{s/\rho}.$$


**Proof. (Garrett, 2012)**

TODO. Basically prove that $(s-1)\zeta(s)$ is entire.

Using equation (Prove $|(s-1)\zeta(s)|\ll_\varepsilon e^{|s|^{\varepsilon+1}}$ for all $\varepsilon>0$ using Euler's reflection formula and the Riemann functional equation) ($\dagger$)
$$\frac{\Gamma(s/2)}{\pi^{s/2}}\zeta(s)=\int_0^\infty x^{s/2}\sum_{n=1}^\infty e^{-n^2\pi x}\frac{dx}{x}=\int_1^\infty(x^{s/2}+x^{(1-s)/2})\sum_{n=1}^\infty e^{- n^2\pi x}\frac{dx}{x}+\frac{1}{s-1}-\frac{1}{s}.$$
Now for $x\geq 1$,
$$\sum_{n=1}^\infty e^{-n^2\pi x}\leq\sum_{n=1}^\infty e^{-n\pi x}=\frac{1}{e^{\pi x}-1}\ll e^{-x}.$$
Let $\sigma>1/2$, then by symmetry
$$\left|\int_1^\infty(x^{s/2}+x^{(1-s)/2})\sum_{n=1}^\infty e^{-\pi n^2 x}\frac{dx}{x}\right|\leq\int_0^\infty x^\sigma e^{-x}\frac{dx}{x}=\Gamma(\sigma),$$
and by Stirling-Laplace,
$$\Gamma(\sigma)\ll_\delta\sigma^{\sigma-1/2}e^{-\sigma}=e^{(\sigma-1/2)\log(\sigma)-\sigma}\ll_\varepsilon e^{|s|^{1+\varepsilon}}.$$
Multiplying by $s(s-1)$ then by the triangle inequality,
$$\left|\frac{s(s-1)\Gamma(s/2)\zeta(s)}{\pi^{s/2}}\right|\leq\left|s(s-1)\int_1^\infty(x^{s/2}+x^{(1-s)/2})\sum_{n=1}^\infty e^{-\pi n^2 x}\frac{dx}{x}\right|+1\ll_\varepsilon e^{|s|^{1+\varepsilon}}.$$
Therefore, Hadamard implies $\Gamma(s/2)\zeta(s)$ admits a product factorisation with linear exponential factors. Combining with the product form for $1/\Gamma(s)$ gives
$$\zeta(s)=e^{a+b s}s\prod_{\rho}\left(1-\frac{s}{\rho}\right)\prod_{n\geq 1}\left(1+\frac{s}{2n}\right)e^{-s/(2n)},$$
where $\zeta(\rho)=0$ and $0<\Re\rho<1$.
\end{proof}
%Consider an arbitrary function of the Hadamard form whose zeros are know to come in conjugate pairs, $\rho_k=u_k+ iv_k$ and $\rho_{-k}=u_k-iv_k$, and where $\rho_0\equiv 1$. Then we can create a new function
%$$Z(s)=\frac{1}{2}\left(\frac{2\pi}{\tau(s)}\right)^s\prod_{k=-\infty}^\infty\left(1-\frac{s}{\rho_k}\right)e^{s/\rho_k},$$
whenever such a function converges. Combining conjugate multiplicands,
$$Z(s)=\frac{1}{2}\left(\frac{2\pi}{\tau(s)}\right)^s\prod_{k=1}^\infty\left(\frac{(s-u_k)^2+v_k^2}{u_k^2+v_k^2}\right)e^{2su_k/(u_k^2+v_k^2)},$$
and simplifying,
$$Z(s)=\frac{1}{2}\left(\frac{2\pi}{\tau(s)}\right)^s\prod_{k=1}^\infty\left(\frac{(s-u_k)^2+v_k^2}{|\rho_k|^2}\right)e^{2su_k/|\rho_k|^2},$$
which can be written as
$$Z(s)=\frac{1}{2}\left(\frac{2\pi}{\tau(s)}\right)^s\prod_{k=1}^\infty\left(1+\frac{s(s-2u_k)}{|\rho_k|^2}\right)e^{2su_k/|\rho_k|^2}.$$
This function is zero if and only if the multiplicand is zero for some $k$, i.e.
$$1+\frac{s(s-2u_k)}{|\rho_k|^2}=0.$$