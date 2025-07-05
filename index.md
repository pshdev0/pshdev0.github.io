# Analytic Number Theory Notes

# Introduction
## The Fundamental Theorem of Arithmetic
TODO - This is central to the work presented.
## Summation
TODO
## Complex Analysis
### Complex numbers
The set of complex numbers, denoted $\mathbb{C}$, are a generalisation of the real numbers $\mathbb{R}$. We define a complex number $z$ by $z=x+iy$ where $x,y$ are real numbers, e.g. $1$,$-4$,$\pi$,$-3/4$, etc. The symbol $i$ may be treated algebraically like any other symbol with the additional property that $i^2=-1$, i.e. $i=\sqrt{-1}$. We can represent a complex number as the ordered pair $z=(x,y)$ and so imagine it in the "complex plane" as a point. Some notation and facts regarding complex numbers are now given:

- $z^*\equiv\bar{z}\equiv x-iy$
- $|z|\equiv\sqrt{zz^*}=\sqrt{(x+iy)(x-iy)}=\sqrt{x^2-xiy+iyx-i^2y^2}=\sqrt{x^2+y^2}$ is the length of the complex number.
- $e^{iz}=\cos z+i\sin z$
- $\Re(z)=x$
- $\Im(z)=y$
- $\text{Arg~}z=\tan_2^{-1}(y/x)$, where $\tan_2$ takes into account the quadrant $z$ belongs to.
- $\log z=\log|z|+i(\text{Arg~}(z)+2\pi k)$, where $k\in\mathbb{Z}$.

### Real \& Complex Calculus
Just as with a real function $g$ of a real variable $x$, denoted $g(x)$, we may consider a complex function $f$ of a complex variable $z$, denoted $f(z)$. We may also integrate such functions. Integrating a real function is simple in the sense we can only integrate over intervals of the real line, but complex numbers exist in a two-dimensional plane, so the path of integration can be a two-dimensional curve. We will want to integrate a complex function around a simple closed contour $\gamma$ ("simple" because it does not intersect itself). An example will demonstrate. Suppose we wish to integrate the function $f(z)$ around the contour $|z|=1$. We write this as
$$I=\oint_\gamma f(z)dz,$$
where $\gamma=\{z:|z|=1\}$. The closed contour $\gamma$ may be parametrized by $\gamma=\{z=e^{i\theta}:0\leq\theta\leq 2\pi\}$, hence $$I=\int_0^{2\pi}f(e^{i\theta})ie^{i\theta}d\theta,$$
which may be evaluated in the usual manner.

A complex function $f(z)$ is "holomorphic" (by analogy "analytic" in real analysis) in a domain $D$ if it is differentiable in $D$, i.e. has no singularities inside $D$. Luckily there's a nice pair of equations called the \emph{Cauchy-Riemann} equations which tell us when a function is holomorphic. Let $f(z)=f(x+iy)=u(x,y)+iv(x,y)$, then $f$ is holomorphic if and only if
$$u_x=v_y\text{~and~}u_y=-v_x,\tag{CR}$$
where $f_x\equiv\partial f/\partial x$ is just partial differentiation. The Cauchy-Goursat theorem tells us that integrating a holomorphic function over a simple closed contour is precisely
$$\int_Cf(z)dz=0.\tag{CG}$$
Cauchy's Integral Formula states that if $f$ is holomorphic then
$$\frac{1}{2\pi i}\int_C\frac{f(z)}{z-z_0}dz=f(z_0),$$
which implies
$$f^{(n)}(z_0)=\frac{n!}{2\pi i}\int_C\frac{f(z)}{(z-z_0)^{n+1}}dz.\tag{CIT}$$
Some consequences of this are (1) if $f$ is once differentiable then it is infinitely differentiable, which is not true in general for real analysis, (2) if $f$ is bounded and differentiable then $f$ is constant, and (3) any $n$-th degree polynomial has $n$ roots. 

In real analysis we say that a function is analytic if and only if it is equal to its power series. But in complex analysis a function is holomorphic function if and only if it is analytic ! Hence, if $f$ is once differentiable then it is automatically equal to its power series. For complex valued functions that are not differentiable, we can construct it's Laurent seres,
$$f(z)=\sum_{n=-\infty}^\infty a_n(z-z_0)^n=\sum_{n=1}^\infty \frac{a_{-n}}{(z-z_0)^n}+\sum_{n=0}^\infty a_n(z-z_0)^n.$$
Amazingly, integrating the Laurent series of a function over a simple closed path $C$ gives the very nice result,
$$\int_Cf(z)dz=\int_C\sum_{n=2}^\infty \frac{a_{-n}}{(z-z_0)^n}dz+\int_C\frac{a_{-1}}{z-z_0}dz+\int_C\sum_{n=0}^\infty a_n(z-z_0)^ndz$$
$$\stackrel{CG}{=}\int_C\frac{a_{-1}}{z-z_0}dz\tag{$\int$-als over holomorphic functions vanish !}$$
$$=2\pi i a_{-1}

$$
where $a_{-1}$ is the coefficient of $1/(z-z_0)$ and is called the residue at $z_0$, denoted $Res(f,z_0)$. Turns out the integral of a complex function around a smooth closed path depends only on the residues contained within it,
$$\int_cf(z)dz=2\pi i\sum_i\text{Res}(f,z_i),$$
where we sum over all singularities of $f$, i.e. points $z_i$ such that $f(z_i)$ is not defined. There are three main types of singularity: (1) a \emph{removable singularity} isn't really a singularity at all, e.g. let
$$f(z)=\frac{(z-z_0)^2}{z-z_0}=z-z_0,$$
so although at $z=z_0$ the function $f$ is not defined (since the denominator would be zero and we can't divide by zero), we can in fact simplify the expression for $f$ and it turns out the function is well-defined at $z=z_0$. (2) a \emph{pole of order $k$} arises for a function whose Laurent series has a finite ``tail'', i.e. $$\frac{1}{z-z_0}+\frac{2}{(z-z_0)^2}+\cdots+\frac{3}{(z-z_0)^k}.$$ (3) the worst type of singularity is the \emph{essential singularity}, e.g.
$$f(z)=e^{1/z}=\sum_{n=0}^\infty\frac{1}{n!}\frac{1}{z^n},$$
whose Laurent series tail is infinite in length.

Let's try to evaluate
$$I=\int_{1/2-i\infty}^{1/2+i\infty}\frac{1}{(z-1)^2+1}dz,$$
i.e. we want to integrate the function $f(z)=1/((z-1)^2+1)$ over the imaginary (vetical) line which passes through $1/2$. We can do this using the residue calculus if we consider integrating $f(z)$ over a simple closed piecewise path consisting of the imaginary line going from $1/2+iR$ down to $1/2-iR$ (this would be the same as $-I$) then along the half circle $1/2+Re^{i\theta}$ where $-\pi\leq\theta\leq\pi$. As $R\to\infty$ the integral along the vertical line corresponds to $-I$ and it turns out the integral along the half circle vanishes, hence by the residue theorem we have $-I+0=\sum\text{Residues}$. But the singularities of $f(z)$ occur at $z=\pm i$, so working out the residues and substituting them into the formula,
$$-I+0=\frac{i}{2}-\frac{i}{2}=0\implies I=0.$$
### Analytic Continuation
### Locally Uniformly Convergence
A complex valued function $f$ of a complex variable is called holomorphic in an open set $U\subset\mathbb{C}$ if $f'(s)$ exists for all $s\in U$. We denote the set of all holomorphic functions in $U$ by $Hol(U)$, which turns out to be a vector space and a metric space. We will require a useful kind of convergence called Locally Uniformly (LU) convergence.
**Definition.** 
	Let $D\subset\mathbb{C}$ be an open set and $f_n:D\to\mathbb{C}$ be a sequence of functions. Then $f_n$ converges to $f:D\to\mathbb{C}$ locally uniformly if for all $P\in D$ there exists a neighborhood $U\subset D$ of $P$ such that $f_n$ converges uniformly to $f$ in $U$.

**Lemma.** 
  Let $U\subset\mathbb{C}$ be an open set. If $f_n\xrightarrow{L.U.} f$ in $U$ then $f_n\in Hol(U)$, $f\in Hol(U)$ and $f_n'\xrightarrow{L.U.}f'$.

## Asymptotic Notation
We write $f=O(g)$ or $f\ll g$ if $|f(x)|\leq A|g(x)|$ for all $x\geq x_0$ for some $x_0$. We may write $O_\varepsilon(g)$ or $f\ll_\varepsilon g$ if the constant $C$ depends on $\varepsilon$. For example $6x\sin x=O(x)$ or $f(x)=O(1)$ implies that $|f(x)|$ is bounded.

By contrast we write $f=o(g)$ if for all $\varepsilon>0$ there exists an $x_0>0$ such that $|f(x)|\leq\varepsilon A|g(x)|$ for all $x\geq x_0$ for some $x_0$ which loosely speaking means that $f$ is \emph{strictly} bounded by $g$.

## The Mellin Transform
The Mellin transform $$\mathcal{M}[f](s) = \int_0^\infty x^{s-1}f(x) dx,$$
or $$\mathcal{M}_1[f](s) = \int_{1}^{\infty}x^{-s-1}f(x)dx$$ is an integral transform such that $\mathbb{R}\rightarrow\mathbb{C}$. We have the following basic properties:

  - $\mathcal{M}_1[1]=\int_1^\infty x^{-s-1}dx=s^{-1}$ for $Re(s)>0$.
  - Linearity: $\mathcal{M}_1[f+g] = \mathcal{M}_1[f]+\mathcal{M}_1[g]$ and $\mathcal{M}_1[\alpha f] = \alpha\mathcal{M}_1[f]$.
  - Injectivity: $\mathcal{M}_1[f]=\mathcal{M}_1[g]$ implies $f=g$.
  - Ramanujan's Master Theorem: $\mathcal{M}\left[\sum_{k=0}^\infty\frac{\varphi(k)}{k!}(-x)^k\right]=\Gamma(s)\varphi(-s)$.

Not sure why the ANT notes use $\mathcal{M}_1$ instead of the more widespread $\mathcal{M}$ ?
The inverse Mellin transform $\mathcal{M}^{-1}$ is
$$f(x)=\frac{1}{2\pi i}\int_{c-i\infty}^{c+i\infty}x^{-s}F(s)ds,$$
where the contour is an imaginary line, e.g. a semi-circle with centre $c$ and radius $R\to\infty$.
## The Gamma Function
**Definition.** [The Gamma Function]
Let $\Re(z)>0$ and define the function
$$\Gamma(z)=\int_0^\infty x^{z-1}e^{-x}dx=\lim_{n\to\infty}\frac{n^z}{z}\prod_{k=1}^n\frac{1}{1+\frac{z}{k}}.$$


**Proposition.** 
Some properties of the gamma function are as follows,

- Functional equation (FE): $\Gamma(1+z)=\int_0^\infty x^z e^{-x}dx\overset{IBP}{=}z\int_0^\infty x^{z-1}e^{-x}dx=z\Gamma(z)$ for $\Re(z)>0$.
- Analytic continuation: 
$\Gamma(z)=\Gamma(1+z)/z$
extends the domain of $\Gamma(z)$ to $\Re(z)>-1$ except for $z=0$. Repeating extends the domain to $\Re(z)>-2$, except for $z=-1$, and so on. In this manner $\Gamma(z)$ may be analytically continued to $\mathbb{C}\setminus\mathbb{Z}_{\leq 0}$.
- Factorial property (FP): By repeated application of the FE, $\Gamma(n)=(n-1)!$ for $n\in\mathbb{N}$.
- Euler's reflection formula: For $z\not\in\mathbb{Z}$.
$$\Gamma(1-z)\Gamma(z)\stackrel{FE}{=}-z\Gamma(-z)\Gamma(z)\stackrel{Def.}=-z\lim_{n\to\infty}\frac{n^z}{z}\prod_{k=1}^n\frac{1}{1+\frac{z}{k}}\lim_{n\to\infty}\frac{n^{-z}}{-z}\prod_{k=1}^n\frac{1}{1-\frac{z}{k}}$$
$$=\lim_{n\to\infty}\frac{1}{z}\prod_{k=1}^\infty\frac{1}{1-\frac{z^2}{k^2}}\stackrel{Euler}{=}\frac{\pi}{\sin(\pi z)}$$

- $1/\Gamma(z)$ is entire: Since $\Gamma(w)$ has no poles for $\Re w>0$ then by Euler's reflection formula $1/\Gamma(-w)=-\Gamma(1+w)\sin(\pi w)/\pi$ has no poles and $1/\Gamma(z)$ is an entire function.
- Legendre's duplication formula: $\Gamma(z)\Gamma(1/2+z)=2^{1-2z}\pi^{1/2}\Gamma(2z)$.
- "Mellin" formula $$\int_0^\infty x^{s/2-1}e^{-n^2\pi x}dx=\mathcal{M}\left[\sum_{k=0}^\infty\frac{(n^2\pi)^k}{k!}(-x)^k\right](s/2)\stackrel{RMT}{=}\frac{\Gamma(s/2)}{n^s\pi^{s/2}}.$$
- Stirling-Laplace asymptotic formula: $\Gamma(z)\sim \sqrt{2\pi}z^{z-1/2}e^{-z}$.

Our first theorem may seem a little esoteric and abstract, but bear with it as it's the "worst" it will get!
**Theorem.** (Hadamard's Factorization Theorem)
Let $f$ be an entire function of finite order $\omega$ and $z_i$ the non-zero zeros of $f$ with multiplicity. Let 0 be a zero of $f$ with multiplicity $m$. Let the \emph{rank} of $f$, $p<\omega$, be the smallest integer $p$ such that
$\sum_{n=1}^\infty1/|z_n|^{p+1}<\infty$. Then there exists a polynomial $g$ whose degree is at most $\omega$ such that
$$f(z)=z^me^{g(z)}\prod_{n=1}^\infty E_p(z/z_n),$$
where $E_p$ is the $p$-th Weierstrass elementary factor, $E_0=1-z$ and $E_p=\exp(z+z^2/2+\cdots+z^p/p)$.


**Proposition.** 
Let $\Re s\geq\delta>0$, then by Stirling-Laplace,
$$\left|\frac{1}{\Gamma(s)}\right|\sim\frac{1}{\sqrt{2\pi}}\left|s^{1/2-s}e^{s}\right|=\frac{1}{\sqrt{2\pi}}\left|e^{-(s-1/2)\log s+s}\right|=\frac{1}{2\pi}\left|e^{-(\sigma-1/2)\log|s|+t\theta+\sigma}\right|.$$
We will show that
$$e^{-(\sigma-1/2)\log|s|+t\theta+\sigma}<Ce^{|s|^{1+\varepsilon}}\equiv e^{c+|s|^{1+\varepsilon}},$$
or equivalently
$\color{ForestGreen}-(\sigma-1/2)\log|s|\color{black}+\color{NavyBlue}t\theta+\sigma\color{black}<c+\color{RedOrange}|s|^{1+\varepsilon}$ for some constant $c>0$ and $x\equiv|s|$ sufficiently large. Since $x>\sigma,t$ and $|\theta|\leq\pi/2$ then wlog we may rewrite
$$\color{ForestGreen}(x+1/2)\log(x)\color{black}+\color{NavyBlue}(\pi/2+1)x\color{black}-\color{RedOrange}x^{1+\varepsilon}\color{black}=x\log(x)-x^{1+\varepsilon}+O(x)\to-\infty,$$
as $x\to\infty$ since $\lim_{x\to\infty}(x\log x)/x^{1+\varepsilon}=0$. Therefore, the right hand side is bounded above and $\Gamma^{-1}(s)\ll_\varepsilon e^{|s|^{1+\varepsilon}}$. Now using Euler's reflection formula and similar reasoning,
$$\left|\frac{1}{\Gamma(1-s)}\right|=\color{ForestGreen}\left|\Gamma(s)\right|\color{NavyBlue}\left|\frac{\sin(\pi s)}{\pi}\right|\color{black}\ll_{\varepsilon}\color{ForestGreen}e^{|s|^{1+\varepsilon}}\color{NavyBlue}e^{\pi|s|}\color{black}\ll_{\varepsilon} e^{|s|^{\varepsilon+1}}.$$
Therefore, since $\Gamma^{-1}(s)$ is an entire function with zeros at the non-positive integers then by Hadamard's factorisation theorem, $$\frac{1}{\Gamma(s)}=e^{a+bs}s\prod_{n=1}^\infty\left(1+\frac{s}{n}\right)e^{-s/n}.$$


# The Infinitude of the Primes
Give the standard argument for the infinitude of the primes.

We can also prove the infinitude of the primes by a more direct approach.
**Theorem.** [Euler c.1737]
  $$\sum_p\frac{1}{p}=\infty.$$

**Proof.**
  We consider
  $$
    \log\left(\frac{1}{1-1/p}\right)-\frac{1}{p},
  $$
  and we have that
  $$
    0<\log\left(\frac{1}{1-1/p}\right).
  $$
  Now, since
  $$
    -\log(1-x)=\sum_{n=1}^\infty\frac{x^n}{n}
  $$
  then
    $$\log\left(\frac{1}{1-1/p}\right)-\frac{1}{p} = -\log(1-1/p)-1/p \sum_{n=2}^\infty\frac{1}{np^n}$$
    $$=\frac{1}{2p^2}+\frac{1}{3p^3}+\frac{1}{4p^4}+\cdots$$
    $$<\frac{1}{2p^2}+\frac{1}{2p^3}+\frac{1}{2p^4}+\cdots$$
    $$=\frac{1}{2p^2}\left(1+\frac{1}{p}+\frac{1}{p^2}+\cdots\right)$$
    $$=\frac{1}{2p^2}\frac{1}{1-1/p} = \frac{1}{2p(p-1)},$$
  and we have that
  $$
    \sum_p\frac{1}{2p(p-1)}<\sum_p\frac{1}{p^2}<\frac{\pi^2}{6}.
  $$
  Hence,
  $$
    \sum_p\left(\log\left(\frac{1}{1-1/p}\right)-\frac{1}{p}\right)
  $$
  converges. Now,
  $$
    \sum_p\log\frac{1}{1-1/p} = \log\prod_p\frac{1}{1-p^{-1}}=\log\zeta(1)=\infty.
  $$
  Now suppose that $\sum_p\frac{1}{p}$ conveges. Then we have a contradiction since
  $$
    divergent series-convergent series=divergent series,
  $$
  so we must have $\sum_p\frac{1}{p}$ is divergent.
\end{proof}
**Theorem.** 
  $$
    \sum_{p\leq x}\frac{1}{p}\geq \log\log x - \log 2.
  $$


\begin{proof}
  Let $n=qm^2$ where $n=q$ is square free, e.g. $12=3\cdot 2^2$. Now,
  $$
    \sum_{n\leq x}\frac{1}{n}<\sum_{q\leq x}\frac{1}{q}\sum_{m\geq 1}\frac{1}{m^2}=\frac{\pi^2}{6}\sum_{q\leq x}\frac{1}{q}<2\sum_{q\leq x}\frac{1}{q},
  $$
  and so
  \begin{eqnarray}
    \label{ref:eq203}
    \sum_{q\leq x}\frac{1}{q} > \frac{1}{2}\sum_{n\leq x}\frac{1}{n}.
  \end{eqnarray}
  We also have
  \begin{eqnarray}
    \label{ref:eq204}
    \sum_{n\leq x}\frac{1}{n}\geq \log x.
  \end{eqnarray}
  Hence,
  $$
    \sum_{p\leq x} \frac{1}{p} > \log\sum_{q\leq x}\frac{1}{q} > \log\left(\sum_{n\leq x}\frac{1}{n}\right)-\log 2 \geq \log\log x - \log 2.
  $$
This theorem also shows that $\sum_p\frac{1}{p}=\infty$.

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

# Analytic/Meromorphic Continuation of $\zeta(s)$
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

# $\zeta$ as a Generating Function
Sequences of numbers may be encoded by what are called \emph{generating functions}. For example, the infinite sequence $(1,1,1,1\ldots)$, may be be encoded by the function $f(z)=1+1\cdot z+1\cdot z^2+1\cdot z^3+\cdots$, where each element in the sequence appears as a coefficeint of a power of $z$, the first element being the coefficient of the monomial $z^0=1$. Moreover, this function representation has the closed form
$$f(z)=\frac{1}{1-z},$$
for $z\neq 1$, so the original infinite sequence of numbers can be represented in a compact closed form. A more complicated generating function, producing the sequence of \emph{Bernoulli numbers} $B_n$, is given by
$$\sum_{n=0}^\infty B_n\frac{z^n}{n!}=\frac{z}{e^z-1}.$$

The question arises of how to obtain sequence elements from a given generating function. One approach is to use Taylor series. Consider the general generating function,
$$f(z)=a_0+a_1z^1+a_2z^2+a_3z^3+O(z^4).$$
How do we get $a_0$? Simple, just compute $f(0)=a_0+0+0+\cdots =a_0$. How about $a_1$? Just compute $f'(0)=a_1+0+0+\cdots=a_1$. We may continue in this way and use the general formula
$$f^{(k)}(0)=k!a_k\implies a_k=\frac{f^{(k)}(0)}{k!}.$$
Another method from complex analysis is Cauchy's integral formula,
$$f^{(k)}(a)=\frac{k!}{2\pi i}\oint_\gamma\frac{f(z)}{(z-a)^{k+1}}dz\implies f^{(k)}(0)=\frac{k!}{2\pi i}\oint_\gamma\frac{f(z)}{z^{k+1}}dz.$$
Using the first aproach and solving for each $B_n$ one obtains the sequence of Bernoulli numbers $$1, -\frac{1}{2}, \frac{1}{6}, 0,-\frac{1}{30}, 0, \frac{1}{42}, 0, -\frac{1}{30}, 0, \frac{5}{66}\ldots,$$ which turn out to be related to $\zeta(s)$ by
$$\zeta(2n)=\frac{(-1)^{n-1}(2\pi)^{2n}B_{2n}}{2(2n)!}\quad\quad\text{~and~}\quad\quad\zeta(1-2n)=-\frac{B_{2n}}{2n},$$
where $n$ is a non-negative integer. Generating functions can also be defined in terms of the $\zeta$ function, e.g.

**Proposition.** 
Let $d(n)$ be the number of divisors of the number $n$, e.g. $d(10)=4$ since $1,2,5,10\mid 10$, then
$$\zeta^2(s)=\sum_{n=1}^\infty\frac{d(n)}{n^s}.$$


\begin{proof}
$$\zeta^2(s)=\sum_{n=1}^\infty\frac{1}{n^s}\sum_{m=1}^\infty\frac{1}{m^s}=\sum_{n=1}^\infty\sum_{m=1}^\infty\frac{1}{(nm)^s},$$
so for every possible way of writing an integer $N$ as a product of two numbers the numerator counts one for that integer $N$, e.g. for $N=15$ we have
$$1(15)=3(5)=5(3)=15(1),$$
so we count 4. All these ``1'''s in the numerators are added together by the sum, so the total of the sum of all numerators for a denominator corresponding to $N=15$ is $d(15)=4$.

Similarly, for $N=100$ we have
$$1(100)=2(50)=4(25)=20(5)=10(10)=5(20)=25(4)=50(2)=100(1),$$
so we count 9. Notice that here $n=m=10$ appear together so this particular pair only gets counted once, unlike in the case for $N=15$.

Therfore, the numerators of a given denominator $N^s$ count the divisors $d(N)$ and we obtain $d(N)/N^s$.
\end{proof}
Hence certain combinations of the $\zeta$ function encode number sequences as the coefficients of $n^{-s}$. This is different to the ordinary generating functions we used earlier which encoded number sequences as the coefficients of $z^n$.
**Proposition.** 
Let $\sigma_a(n)$ be the sum of divisors of $n$ each raised to power $a$, e.g. $\sigma_2(8)=1^2+2^2+4^2+8^2$, then
$$\zeta(s)\zeta(s-a)=\sum_{n=1}^\infty\frac{\sigma_a(n)}{n^s}.$$

**Proof.**
$$\sum_{n=1}^\infty\frac{1}{n^s}\sum_{m=1}^\infty\frac{1}{m^{s-a}}=\sum_{n=1}^\infty\sum_{m=1}^\infty\frac{m^a}{(nm)^s},$$
so for every possible way of writing an integer $N$ as a product of two numbers we count $m^a$ for that integer $N$, e.g. for $N=15$ the $nm$ pairs are $1(15)=3(5)=5(3)=15(1)$ so we count $15^a+5^a+3^a+1^a$.

Using Hadamard's proof earlier we showed that $\zeta(1+it)\neq 0$. The above proposition can be used as a starting point to prove the very same result, and is known as Ikeharah's Theorem\footnote{Wiener, N., 1988. The Fourier integral and certain of its applications. CUP Archive, pp. 125-137.}
**Proposition.**
Let $\omega(n)$ be the number of distinct prime factors of $n$, e.g. $\omega(10)=\omega(2\cdot 5)=2$, then
$$\frac{\zeta^2(s)}{\zeta(2s)}=\sum_{n=1}^\infty\frac{2^{\omega(n)}}{n^s}.$$

**Proof.**
Using Euler's product formula,
$$\frac{\zeta^2(s)}{\zeta(2s)}=\prod_p\frac{(1-p^{-s})^{-2}}{(1-p^{-2s})^{-1}}=\prod_p\frac{(1-p^{-2s})}{(1-p^{-s})^2}=\prod_p\frac{(1-p^{-s})(1+p^{-s})}{(1-p^{-s})^2}$$

Canceling $(1-p^{-s})$ and expanding,
$$\prod_p\frac{1+p^{-s}}{1-p^{-s}}=\prod_p(1+p^{-s}+p^{-2s}+\cdots)(1+p^{-s})$$
$$=\prod_p(1+p^{-s}+p^{-2s}+\cdots+p^{-s}+p^{-2s}+p^{-3s}+\cdots$$
$$=\prod_p(1+2p^{-s}+2p^{-2s}+2p^{-3s}+\cdots).$$

Expanding the product gives a sum with terms of the form
$$\frac{2\cdot 2\cdot 2\cdots 2}{p_1^{r_1s}p_2^{r_2s}p_3^{r_3s}\cdots p_k^{r_ks}}=\frac{2^{\omega(p_1^{r_1}p_2^{r_2}p_3^{r_3}\cdots p_k^{r_k})}}{(p_1^{r_1}p_2^{r_2}p_3^{r_3}\cdots p_k^{r_k})^s}=\frac{2^{\omega(n)}}{n^s},$$
by the Fundamental Theorem of Arithmetic (FTA).

**Proposition.** 
Let the M\"{o}bious function $\mu(n)$ be defined

$$
\mu(n) =
\begin{cases}
1 & \text{if } n = 1 \\\\
(-1)^k & \text{if } n \text{ is the product of } k \text{ distinct primes} \\\\
0 & \text{if } n \text{ has a repeated prime factor}
\end{cases}
$$

For example, $\mu(10) = \mu(2 \cdot 5) = 1$, $\mu(11) = -1$, and $\mu(12) = \mu(2^2 \cdot 3) = 0$.

Then:

$$
\frac{1}{\zeta(s)} = \sum_{n=1}^{\infty} \frac{\mu(n)}{n^s}
$$

\begin{proof}
$$\frac{1}{\zeta(s)}=\frac{1}{\prod_p(1-p^{-s})^{-1}}=\prod_p(1-p^{-s})=\left(1-\frac{1}{2^s}\right)\left(1-\frac{1}{3^s}\right)\left(1-\frac{1}{5^s}\right)\cdots.$$
Expanding the product gives a sum whose terms are multiples of the reciprocal primes, so a typical term is
$$\frac{(-1)^k}{(p_1p_2p_3\cdots p_k)^s}=\frac{(-1)^k}{N^s},$$
where the numerator is $-1$ for odd $k$ and $+1$ for even $k$, e.g. $-1/2^s\cdot-1/3^s=(-1)^2/6^s$ and $-1/2^s\cdot-1/3^s\cdot-1/5^s=(-1)^3/30^s$. Furthermore, there are no repeated powers. Hence, by definition of $\mu(n)$ we have the result.
\end{proof}
We can define the M\"{o}bius function in terms of $\omega$ by
$$\mu(n)=\left\{\begin{array}{ll}(-1)^{\omega(n)}&\text{if m is square-free}\\0&\text{otherwise}\end{array}\right.$$
Another\footnote{* Include these two properly...} multiplicative function is the Liouville function defined by $\lambda(n)=(-1)^{\Omega(n)}$.
**Lemma.** 
We have
$$\sum_{d\mid n}\mu(d)=\left\{\begin{matrix}1&if&n=1\\0&if&n> 1\end{matrix}\right..$$


\begin{proof}
  Suppose $n=p_1^{a_1}\cdots p_k^{a_k}$, then
$$\sum_{d\mid n}\mu(d) = 1+\sum_{i=1}^k\mu\left(\prod_{j=1}^i p_j\right) = 1+\sum_{i=1}^k{k\choose i}(-1)^i = \sum_{i=0}^k{k\choose i}(-1)^i 1^{k-i} = 0.$$
\end{proof}
**Proposition.** 
Define the Von-Mangoldt function,
  $$
  \Lambda_{(n)}= \left\{\begin{array}{ll}\log p &if n=p^k\\ 0 & otherwise\end{array}\right.,
$$
then
  $$
    -\frac{\zeta'(s)}{\zeta(s)}=\sum_{n\geq 1}\frac{\Lambda_{(n)}}{n^s}.
  $$


\begin{proof}
Consider the logarithm of Euler's product of $\zeta(s)$,
$$
  \log\zeta(s) = -\sum_p\log(1-p^{-s}).
$$
Differentiating gives
$$
  \frac{\zeta'(s)}{\zeta(s)}=\sum_p - \frac{p^{-s}}{1-p^{-s}}\log p=\sum_p -\log(p)\sum_{k\geq 1}p^{-ks},
$$
which can be rewritten
$$-\sum_p\sum_{k\geq 1}\frac{\log(p)}{p^{ks}}=-\sum_p\sum_{k\geq 1}\frac{\Lambda_{(p^k)}}{(p^k)^s}
    =-\sum_{n=1}^\infty\frac{\Lambda_{(n)}}{n^s}.
$$
\end{proof}
\begin{corollary}
Let $x=\sigma>1$, then
$$
  \frac{\zeta'(x)}{\zeta(x)}=-\sum_{n\geq 1}\frac{\Lambda_{(n)}}{n^x}<0
$$
since the sum is positive. Now, since $\zeta(s)\neq 0$ in $\sigma>1$ then
$$
  \frac{\zeta'(x)}{\zeta(x)}<0,
$$
which implies $\zeta'(x)<0$.
\end{corollary}

Suppose $F(s)=\sum_{n=1}^\infty f(n)/n^s$, then the $f(n)$ may be extracted by the following limiting process,
$$f(x)=\lim_{s\to\infty}x^s\left(F(s)-\sum_{k=1}^n\frac{f(k)}{k^s}\right).$$
**Theorem.** [Apostol, p. 242]
Assume the series $F(s)=\sum_{n=1}^\infty f(n)n^{-s}$ converges absolutely for $\sigma>\sigma_a$. Then for $\sigma>\sigma_a$ and $x>0$ we have
$$\lim_{T\to\infty}\frac{1}{2T}\int_{-T}^T F(\sigma+it)x^{\sigma+it}
dt=\left\{\begin{array}{ll}f(n)&if x=n\\0&otherwise\end{array}\right..$$




# Arithmetic Functions
Material from the previous chapter may be described in a more general framework of arithmetic functions which we study next. An arithmetic function is simply a function $f:\mathbb{N}\mapsto\mathbb{C}$, i.e. a function whose domain is the natural numbers and whose codomain is the complex numbers. We met a bunch of arithmetic functions in the previous sections such as $d(n)$, $\sigma(n)$, $\varphi(n)$, $\omega(n)$, and so on. We introduce a few more here: 


- $\Omega(n)=\sum_{p^a\mid\mid n}a$, where $p^a\mid\mid n$ is the largest power of $p$ which divides $n$, e.g. $\Omega(39375)=\Omega(3^2\times 5^4\times 7^1)=2+4+1=7$.
- $1(n)=1$ for all $n\geq 1$
- $j(n)=n$ for all $n\geq 1$
- $\delta(n)=\left\{\begin{array}{lll}1&:&n=1\\0&:&otherwise\end{array}\right.$.

To each arithmetic function we define the associated Dirichlet series
$$D_f(s)=\sum_{n=1}^\infty\frac{f(n)}{n^s},$$
for those $s\in\mathbb{C}$ for which the series converges. When $f=1$ we obtain $D_1(s)=\zeta(s)$.
Complementary to the Cauchy product (addition) $$\sum_{n=0}^\infty\sum_{n+m=N}a_nb_m,$$ which is useful for multiplying power series, we define the Dirichlet product (multiplication), $$\sum_{N=1}^\infty\sum_{nm=N}a_nb_m,$$ which we will find useful for multiplying Dirichlet series, i.e.

$$D_f(s)D_g(s)=\sum_{n=1}^\infty\frac{f(n)}{n^s}\sum_{m=1}^\infty\frac{g(m)}{m^s}$$
$$=\sum_{N=1}^\infty\sum_{nm=N}\frac{f(n)g(m)}{n^sm^s}$$
$$=\sum_{N=1}^\infty\frac{1}{N^s}\sum_{nm=N}f(n)g(m)$$
$$\equiv\sum_{N=1}^\infty\frac{1}{N^s}(f*g)(N),$$

where we have defined the Dirichlet convolution,
$$(f*g)(n)=\sum_{ab=n}f(a)g(b),$$
which can be rewritten as
$$(f*g)(n)=\sum_{db=n}f(d)g(b)=\sum_{d\mid n}f(d)g\left(\frac{n}{d}\right)=\sum_{d\mid n}f\left(\frac{n}{d}\right)g(d),$$
since $db=n\implies d\mid n$ and $b=n/d$, and similarly for the last sum.
Using Dirichlet convolution, we obtain
$$D_f(s)D_g(s)=D_{f*g}(s).$$

Turns out many arithmetic functions may be built using Dirichlet convolution of simpler arithmetic functions, e.g.
$$(1*1)(n)=\sum_{d\mid n}1(d)1(n/d)=\sum_{d\mid n}1=d(n),$$
so $1*1=d$, and
$$(1*j^k)(n)=\sum_{d\mid n}j^k(d)1(n/d)=\sum_{d\mid n}d^k=\sigma_k(n).$$
Now, using $d=1*1$ then
$$\sum_{n=1}^\infty\frac{d(n)}{n^s}=D_d(s)=D_{1*1}(s)=D_1(s)D_1(s)=\zeta(s)\zeta(s)=\zeta^2(s),$$
which is a much easier way than our previous approach. Also,

$$\sum_{n=1}^\infty\frac{\sigma_k(n)}{n^s}=D_{\sigma_k}(n)=D_{1*j^k}(s)=D_1(s)D_{j^k}(s)$$

$$=\zeta(s)\sum_{n=1}^\infty\frac{j^k(n)}{n^s}=\zeta(s)\sum_{n=1}^\infty\frac{n^k}{n^s}=\zeta(s)\zeta(s-k).$$

Combining three arithmetic functions by convolution,

$$(f*g)*h(n)=\sum_{ab=n}(f*g)(a)h(b)$$
$$=\sum_{ab=n}\left(\sum_{cd=a}f(c)g(d)\right)h(b)$$
$$=\sum_{cdb=n}f(c)g(d)h(b),$$

so that $(f*g)*h=f*(g*h)$, which implies Dirichlet convolution is associative. If we define $$d_k(n)=\sum_{a_1a_2\cdots a_k=n}1=\sum 1(a_1)1(a_2)\cdots 1(a_k)=1*1*`\cdots*`1,$$
then
$$\sum_{n=1}^\infty\frac{d_k(n)}{n^s}=D_{1*1*`\cdots*`1}(s)=\prod_{n=1}^k D_1(s)=D_1^k(s)=\zeta^k(s).$$

Given an arithmetic function $f$, we may be able to factorise it into simpler arithmetic functions, which is simpler when $f$ is of the following form:

- $f$ is \emph{multiplicative} iff $f(mn)=f(m)f(n)$ when $\gcd(m,n)=1$
- $f$ is \emph{completely multiplicative} iff $f(mn)=f(m)f(n)$ for all $m,n\geq 1$
- $f$ is strongly multiplicative iff $f(p^r)=f(p)$ for all primes $p$ and $r\geq 1$
- $g$ is \emph{additive} iff $g(mn)=g(m)+g(n)$ when $\gcd(m,n)=1$
- $g$ is \emph{completely additive} iff $g(mn)=g(m)+g(n)$ for all $m,n\geq 1$
- $g$ is \emph{strongly additive} iff $g(p^r)=g(p)$ for all primes $p$ and $r\geq 1$.

We may examine what happens to a general number under these different types of function. Writing the positive integer $n=p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r}$. where $p_i$ are distinct primes, then we observe the following

- $f$ multiplicative implies $f(n)=f(p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r})=\prod_{k=1}^rf(p_k^{a_k})$ since $\gcd(p_i^{a_i},p_j^{a_j})=1$ for $i\neq j$ but $\gcd(p^a,p^b)\neq 1$. We can also write this in the form $f(n)=\prod_{p^a\mid\mid n}f(p^a)$
- $f$ completely multiplicative implies $f(n)=\prod_{k=1}^rf(p_k)^{a_k}=\prod_{p^a\mid\mid n}f(p)^a$
- $f$ strongly multiplicative implies $f(n)=\prod_{k=1}^rf(p_i)=\prod_{p^a\mid\mid n}f(p)=\prod_{p\mid n}f(p)$
- $g$ additive implies $g(n)=g(p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r})=\sum_{k=1}^rg(p_k^{a_k})=\sum_{p^a\mid\mid n}g(p^a)$
- $g$ completely additive implies $$g(n)=g(p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r})=\sum_{k=1}^rg(p_k^{a_k})=\sum_{k=1}^r\sum_{\ell=1}^{a_k}g(p_k)=\sum_{k=1}^ra_kg(p_k)=\sum_{p^a\mid\mid n}g(p)$$
- $g$ strongly additive implies $g(n)=\sum_{k=1}^rg(p_k)=\sum_{p^a\mid\mid n}g(p)=\sum_{p\mid n}g(p)$.


Turns out $1,j,j^z$ are all strongly multiplicative, whereas $\omega,\Omega$ are additive.

**Theorem.** 
$f,g$ multiplicative implies $f*g$ multiplicative.

**Proof.** TODO

**Theorem.** 
$f$ multiplicative and $D_f(s)$ absolutely convergent at $s_0\in\mathbb{C}$ implies
$$D_f(s)=\prod_p\left(1+\sum_{k\geq 1}\frac{f(p^k)}{p^{ks}}\right),$$
for all $s\in\mathbb{C}$ and $\Re s>\Re s_0$. Moreover, if $f$ is completely multiplicative then the Euler product equals
$$\prod_p\left(1+\sum_{k\geq 1}\frac{f(p)^k}{p^{ks}}\right)=\prod_p\frac{1}{1-\frac{f(p)}{p^s}}=\prod_p\left(1-\frac{f(p)}{p^s}\right)^{-1}.$$

**Proof.** TODO

By definition, a converging Euler product is non-zero.

**Theorem.** 
Suppose
$$\sum_{n=1}^\infty\frac{f(n)}{n^s}=\sum_{n=1}^\infty\frac{g(n)}{n^s},$$
for all $s\in D\subset\mathbb{C}$, then $a_n=b_n$ for all $n\geq 1$.

**Proof.** TODO

**Theorem.** [M\"{o}bius Inversion]
$\delta=1*\mu$ with $\delta$ the identity under *, so that $\mu$ is the inverse of 1 under *, or in other words
$$\sum_{d\mid n}\mu(d)=\delta(n).$$


**Proof.**
Since $D_\delta(s)=1$ and

$$1=\zeta(s)\frac{1}{\zeta(s)}=D_1(s)D_\mu(s)=D_{1*\mu}(s),$$
then $\delta=1*\mu$. For the identity,
$$(f*\delta)(n)=\sum_{d\mid n}f(d)\delta(n/d)=\sum_{d=n}f(d)\delta(n/d)=f(n),$$
and similarly $(`\delta*`f)(n)=f(n)$, so $\delta$ is the identity element under *.
\end{proof}
A Dirichlet inverse of an arithmetic function exists if and only if $f(1)\neq 0$.
\begin{corollary}
Let $f,g$ be arithmetic functions, then $f=1*g$ if and only if $g=\mu *f$.
\end{corollary}
\begin{proof}Suppose $f=1*g$, then $`\mu*`f=`\mu*`(1*g)=(`\mu*`1)*g=`\delta*`g=g$. Now suppose $g=`\mu*`f$, then $1*g=1*(`\mu*`f)=(1*\mu)*f=`\delta*`f=f$.
\end{proof}

A number $n=p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r}$ is said to be $k$-free if and only if $a_i<k$ for all $i\geq 1$, i.e. no $k$-th power divides $n$. We define the characteristic function for $k$-free numbers by\footnote{Note this notation is not universal. Other notations include $|\mu(n)|$ and $\mu^2(n)$, with no such alternatives for $Q_k(n)$ when $k>2$.}
$$Q_k(1)=1 and Q_k(n)=\left\{\begin{array}{lll}1&:&n is k-free\\0&:&otherwise\end{array}\right..$$
**Proposition.**  A number $n$ is said to be square-free if no square divides $n$, for which we use the characteristic function $Q_2(n)$. Let
$$\mu_2(n)=\left\{\begin{array}{ll}\mu(m)&if n=m^2\\0&otherwise\end{array}\right.,$$
then $Q_2=1*\mu_2$.


\begin{proof}
Since $Q_2(p)=1$ and $1(p)=1$ for all primes $p$, suppose there exists an arithmetic function $f$ such that $Q_2=1*f$. Applying M\"{o}bius inversion, $\mu *Q_2=(`\mu*`1)*f=`\delta*`f=f$. Since $\mu$ and $Q_2$ are multiplicative, so is $`\mu*`Q_2$, so we only need to look at prime power arguments. Let $p$ be prime and $r\geq 1$, then by definition
$$`\mu*`Q_2(p^r)=\sum_{d\mid p^r}\mu\left(\frac{p^r}{d}\right)Q_2(d)=\sum_{k=0}^r\mu(p^k)Q_2(p^k).$$
But since $Q_2(p^k)=0$ for $k>1$ then
$$\mu(p^r)Q_2(1)+\mu(p^{r-1})Q_2(p)=\mu(p^r)+\mu(p^{r-1}).$$
By definition $\mu(p^r)=(-1)^r$ when $r\in\{0,1\}$ and $\mu(p^r)=0$ otherwise, so $f(p^r)=-1$ for $r=2$ and $f(p^r)=0$ otherwise. So, for a general number $n=p_1^{a_1}p_2^{a_2}\cdots p_r^{a_r}$, since $f$ is multiplicative,
$$f(n)=f(p_1^{a_1})f(p_2^{a_2})\cdots f(p_r^{a_r})=\left\{\begin{array}{ll}\mu(m)&if n=m^2\\0&otherwise\end{array}\right.\equiv\mu_2.$$
Hence, $Q_2=1*\mu_2$.
\end{proof}
The result
$$Q_2(n)=(1*\mu_2)(n)=\sum_{d\mid n}\mu_2(d)=\sum_{d^2\mid n}\mu(d),$$
is equivalent to
$$D_{Q_2}(s)=D_{1*\mu_2}(s)=D_1(s)D_{\mu_2}(s)=\zeta(s)\sum_{n=1}^\infty\frac{\mu_2(n)}{n^s}=\sum_{m=1}^\infty\frac{\mu(m)}{m^{2s}}=\frac{\zeta(s)}{\zeta(2s)},$$
so we can see how certain arithmetic functions give Dirichlet series whose arguments are multiples of $s$.

Given an arithmetic function $f$ can we get an indication that it can be factorised? If $f$ is multiplicative, then one method is to use the Dirichlet series and Euler products.

**Proposition.** Let $\Re s>1$, then $$\sum_{n=1}^\infty\frac{Q_k(n)}{n^s}=\frac{\zeta(s)}{\zeta(ks)}.$$

**Proof.** Since $Q_k$ is multiplicative, then formally
$$\sum_{n=1}^\infty\frac{Q_k(n)}{n^s}=\prod_p\left(1+\sum_{\ell\geq 1}\frac{Q_k(p^\ell)}{p^{\ell s}}\right)=\prod_p\left(1+\sum_{1\leq\ell<k}\frac{Q_k(p^\ell)}{p^{\ell s}}\right),$$
where the sum is truncated since $Q_k(p^\ell)=0$ for $\ell\geq k$. Expanding the sum,
$$\prod_p\left(1+\frac{1}{p^s}+\frac{1}{p^{2s}}+\cdots+\frac{1}{p^{(k-1)s}}\right)=\prod_p\frac{1-\frac{1}{p^{ks}}}{1-\frac{1}{p^s}}=\frac{\zeta(s)}{\zeta(ks)}.$$

Note that\footnote{Move this !}
$$\frac{1}{\zeta(ks)}=\sum_{m=1}^\infty\frac{\mu(m)}{m^{ks}}=\sum_{n=1}^\infty\frac{\mu_k(n)}{n^s},$$
where
$$\mu_k(n)=\left\{\begin{array}{ll}\mu(m)&if n=m^k\\0&otherwise\end{array}\right.,$$
and $\mu\equiv\mu_1$ is the M\"{o}bius function. Hence,

$$\frac{\zeta(s)}{\zeta(ks)}=D_1(s)D_{\mu_k}(s)=D_{1*\mu_k}(s)=\sum_{n=1}^\infty\frac{(1*\mu_k)(n)}{n^s},$$
hence by theorem (which ?) we have $Q_k=1*\mu_k$.

The general method demonstrated is to find a closed form for the summation, which then reveals a product involving factors which may be manipulated into various different $\zeta$ functions, in this case $\zeta(s)$ and $1/\zeta(ks)$.\footnote{Perhaps move some of the more complicated ones down from the earlier proofs in previous chapter?}. For example, recall theorem\footnote{which?} from earlier, which we will now prove ``in reverse'' using the described method.
$$\sum_{n=1}^\infty\frac{2^\omega(n)}{n^s}=\prod_p\left(1+\frac{2^{\omega(p)}}{p^s}+\frac{2^{\omega(p^2)}}{p^{2s}}+\cdots\right)=\prod_p\left(1+\frac{2}{p^s}+\frac{2}{p^{2s}}+\cdots\right).$$
Substituting $y=1/p^s$, the relevant sum is
$$1+2y+2y^2+2y^3+\cdots=\frac{1+y}{1-y}.$$
Hence, $$\sum_{n=1}^\infty\frac{2^\omega(n)}{n^s}=\prod_p\frac{1+1/p^s}{1-1/p^s}=\prod_p\frac{1+1/p^s}{1-1/p^s}\frac{1-1/p^s}{1-1/p^s}=\prod_p\frac{1-1/p^{2s}}{(1-1/p^s)^2}=\frac{\zeta^2(s)}{\zeta(2s)}.$$
Moreover,
$$D_{2^\omega(n)}(s)=D_1(s)D_1(s)D_{\mu_2}(s)=D_{1*1*\mu_2}(s),$$
hence
$2^{\omega(n)}=1*1*\mu_2$.
**Lemma.** 
Let \emph{Euler's totient function} $\varphi(n)$ be the number of positive integers $\leq n$ that are relatively prime to $n$, i.e. $\gcd(n,k)=1$. For example, $\varphi(4)=2$ since $1,3$ are relatively prime to $n=4$, or $\varphi(8)=4$ since $1,3,5,7$ are relatively prime. Then $\varphi=`\mu*`j$, i.e.
$$\varphi(n)=\sum_{d\mid N}\frac{n}{d}\mu(d)=\sum_{d\mid N}d\mu\left(\frac{n}{d}\right).$$


\begin{proof}
If $r,n$ are relatively prime then $\gcd(r,n)=1$ so by definition $\delta(\gcd(r,n))$ counts only relatively prime pairs $(r,n)$. Hence
$$\varphi(n)=\sum_{r=1}^n\delta(\gcd(r,n))$$
Applying M\"{o}bius inversion $\delta=1*\mu$ (Theorem\footnote{which?}), then
$$\varphi(n)=\sum_{r=1}^n\sum_{d\mid\gcd(r,n)}\mu(d).$$
But\footnote{is this correct?} $d\mid\gcd(r,n)\iff d\mid n$ and $d\mid r$, so
$$\varphi(n)=\sum_{d\mid n}\mu(d)\sum_{\substack{r=1\\d\mid r}}^n 1=\sum_{d\mid n}\mu(d)\frac{n}{d}.$$
\end{proof}
**Proposition.** We have
$$\frac{\zeta(s-1)}{\zeta(s)}=\sum_{n=1}^\infty\frac{\varphi(n)}{n^s}.$$

**Proof**
$$D_\varphi(s)=D_{`\mu*`j}(s)=D_\mu(s)D_j(s)=\frac{1}{\zeta(s)}\zeta(s-1).$$

**Proposition. (Ramanujan - see B. M. Wilson, Proofs of Some Formulæ Enunciated by Ramanujan, Proceedings of the London Mathematical Society, Volume s2-21, Issue 1, 1923, Pages 235–255, https://doi.org/10.1112/plms/s2-21.1.235)**

$$\frac{\zeta(s)\zeta(s-a)\zeta(s-b)\zeta(s-a-b)}{\zeta(2s-a-b)}=\sum_{n=1}^\infty\frac{\sigma_a(n)\sigma_b(n)}{n^s}.$$

**Proof. (is this the one I was working on? - perhaps need to finish...)**
Define $$f^{(k)}(n)=\left\{\begin{array}{ll}f(N)&if n=N^k\\0&otherwise\end{array}\right..$$
Then
$$\zeta(2s)\zeta(s)\zeta(s-a)\zeta(s)\zeta(s-b)\zeta(s)\zeta(s-a-b)=\zeta(s)\zeta(s)\zeta(2s)\zeta(2s-a-b)\sum_{n=1}^\infty\frac{\sigma_a(n)\sigma_b(n)}{n^s},$$
which can be rewritten $D_{1^{(2)}}D_{\sigma_a}D_{\sigma_b}D_{\sigma_{a+b}}=D_{\sigma_{a+b}^{(2)}}D_1D_1D_{\sigma_a\sigma_b}$, or
$$1^{(2)}*\sigma_a*\sigma_b*\sigma_{a+b}=\sigma_{a+b}^{(2)}*1*1*\sigma_a\sigma_b,$$
or
$$1^{(2)}*1*j^a*1*j^b*1*j^{a+b}=\sigma_{a+b}^{(2)}*1*1*\sigma_a\sigma_b,$$
or
$$1^{(2)}*1*j^a*j^b*j^{a+b}=\sigma_{a+b}^{(2)}*\sigma_a\sigma_b.$$
or
$$\sum_{u^2vwxy=n}w^ax^by^{a+b}=\sum_{u^2v=n}\sigma_{a+b}(u)\sigma_a(v)\sigma_b(v).$$

Was I thinking aloud here? - Now let $a=0$, $b=1$ then using Lagarias' inequality (2002),
$$\sum_{u^2vwp=n}p=\sum_{u^2v=n}\sigma(u)\sigma(v)d(v).$$

**Proposition.** 
Let $\ell(n)=\log n$, then $\ell=1*\Lambda$ where $\Lambda$ is the Von-Mangoldt function.


\begin{proof}
Let $n=p_1^{a_1}p_2^{a_2}\cdots P_r^{a_r}$, then
$$1*\Lambda=\sum_{d\mid n}1(n/d)\Lambda(d)=\sum_{d\mid n}\Lambda(d)=\sum_{k=1}^r\sum_{\ell=1}^{a_r}\log p_k=\sum_{k=1}^r\log p_k^{a_r}=\log n.$$

\end{proof}
I was wondering which arithmetic function corresponds to the Dirichlet series $\zeta(bs-a)$ or $1/\zeta(bs-a)$. I can create two arithmetic functions,
$$f_{a,b}(n)=\left\{\begin{array}{ll}m^a\mu(m)&if n=m^b\\0&otherwise\end{array}\right.,$$
and
$$g_{a,b}(n)=\left\{\begin{array}{ll}m^a&if n=m^b\\0&otherwise\end{array}\right.,$$
which give
$$D_f(s)=\sum_{n=1}^\infty\frac{f_{a,b}(n)}{n^s}=\sum_{m=1}^\infty\frac{m^a\mu(m)}{m^{bs}}=\frac{1}{\zeta(bs-a)},$$
and
$$D_g(s)=\sum_{n=1}^\infty\frac{g_{a,b}(n)}{n^s}=\sum_{m=1}^\infty\frac{m^a}{m^{bs}}=\zeta(bs-a),$$
but then how can we factorise $f$ or $g$ ? Are they even multiplicative ?
## Dirichlet eta function
Let $f(n)=(-1)^{n-1}$.

$$f(n)+f(m)=(-1)^n+(-1)^m=(-1)^n(1+(-1)^{m-n}).$$
$$f(n)f(m)=(-1)^n(-1)^m=(-1)^{n+m}=f(n+m).$$

Let $\gcd(n,m)=1$ then $f(nm)=(-1)^{nm}=((-1)^n)^m$.
# Some Asymptotic Results
When exact results seem intractable, it may be instructive to prove asymptotic results first. We will make use of "Big-O" notation. In this section we will use the notations

$$\Psi(x)=\sum_{n\leq x}\Lambda(n),\quad\theta(x)=\sum_{p\leq x}\log p,\quad\text{~and~}\quad\pi(x)=\sum_{p\leq x}1.$$

**Theorem.** 
$$\sum_{d\leq x}d(n)=x\log x+O(x).$$

**Proof.**
We can write
$$\sum_{n\geq x}d(n)=\sum_{n\geq x}\sum_{d\mid n}1=\sum_{d\leq x}\sum_{\substack{d\mid n\\n\leq x}}1=\sum_{d\leq x}\left[\frac{x}{d}\right],$$
then since $[y]=y+\{y\}=y+O(1)$,
$$\sum_{d\leq x}\left(\frac{x}{d}+O(1)\right)=x\sum_{d\leq x}\frac{1}{d}+O\left(\sum_{d\leq x}1\right).$$
Hence,
$$x(\log x+O(1))+O(x)=x\log x+O(x).$$

**TODO.** Inlcude sums of arithmetic functions - there is an asymptotic result !

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


# The Music of the Primes
Let's examine the term
$$
  -\frac{1}{2}\log\left(1-\frac{1}{x^2}\right)
$$
further. Expanding
$$
  \frac{1}{2x^2}+\frac{1}{4x^4}+\frac{1}{6x^6}+\cdots = \sum_{n\geq 1}\frac{x^{-2n}}{2n}=-\sum_{n\geq 1}\frac{x^{-2n}}{-2n} = -\sum\frac{x^\rho}{\rho},
$$
where $\rho$ are the trivial zeros of $\zeta$, so we could in fact rewrite the explicit formula as
$$
  \psi(x) = x - \sum_{\zeta(\rho)=0}\frac{x^\rho}{\rho}-\log(2\pi),
$$
where $\rho$ are all the zeros of $\zeta$, but we choose not to do this as the non-trivial zero contribution tends to zero as $x\to\infty$.

Now let's look at the non-trivial zeros $\rho$ which come in conjugate pairs,

$$\frac{x^\rho}{\rho}+\frac{x^{\bar{\rho}}}{\bar{\rho}} = \frac{x^{\beta+i\gamma}}{\beta+i\gamma}+\frac{x^{\beta-i\gamma}}{\beta-i\gamma}=\frac{2x^\beta}{|\rho|}\left(\frac{\beta}{|\rho|}\cos(\gamma\log x)+\frac{\gamma}{|\rho|}\sin(\gamma\log x)\right),$$

which we can rewrite as

$$\frac{2x^\beta}{|\rho|}\cos(\gamma\log x - \text{tan}^{-1}(\gamma/\beta)).$$

Now if the RH is true then all non-trivial zeros are such that $\beta=1/2$, so that
$$\frac{x^\rho}{\rho}+\frac{x^{\bar{\rho}}}{\bar{\rho}} =\frac{2x^{1/2}}{|\rho|}\cos\left(\gamma\log x-\tan^{-1}(2\gamma)\right).$$
The envelope of this curve is $y^2=\pm4x/|\rho|^2$, and as $|\rho|$ increases the parabola gets closer and closer to the $x$-axis. Now consider the logarithmic scale where $t=\log x$ so that
$$\frac{2e^{t/2}}{|\rho|}\cos(\gamma t-\theta),$$
where $\theta=\tan^{-1}(2\gamma)$. This summand in the explicit formula has phase shift $\theta$ and amplitude $2e^{t/2}/|\rho|$. Consider $\cos(\gamma t-\theta)=0$ which happens when $\gamma t-\theta=(2n+1)\pi/2$. Hence,
$$\log x=\frac{2n+1}{2}\frac{\pi}{\gamma}+\frac{\theta}{\gamma},$$
which implies $x=e^{\theta/\gamma}e^{(2n+1)\pi/(2\gamma)}$ for all $n\geq 1$. Now, since $|\rho|=\sqrt{1/4+\gamma^2}\approx\gamma$ then the amplitude of the oscillatory term is
$$\frac{2e^{t/2}}{|\rho|}\approx\frac{2e^{t/2}}{\gamma}.$$

TODO: List first few zeros of $\zeta(s)$ ? ...

Now, back to equation (1) where the left hand side is a step function and the right hand side contains the oscillatory terms with amplitudes $2e^{t/2}/|\rho|$ (assuming RH). For a fixed non-trivial zero $\rho$ the amplitude increases with $t$, known as a ``crescendo.'' An $\alpha$-crescendo is a ratio $\alpha$ of the amplitudes taken over a time delay of one second. For example at an initial time $T$ a 2-crescendo is
$$\frac{2e^{(T+1)/2}}{|\rho|}/\frac{2e^{T/2}}{|\rho|}=\sqrt{e}.$$
Each conjugate pair of non-trivial Riemann zeros give rise to a "pure note" with a $\sqrt{e}$-crescendo, and as $t$ increases the loudness of this note increases at a constant rate. The ``Music of the Primes'' refers to the oscillatory term in the Von-Mangoldt explicit formula. The first non-trivial zero gives a fundamental frequency, with the harmonies given by the other zeros.

Now, using equation (1) let $\rho=1/2+i\gamma$, then if the Riemann Hypothesis is true then $$\frac{\psi(x)-x}{\sqrt{x}}=-\sum\frac{x^{i\gamma}}{\rho}+O(1)\tag{2}.$$
Writing the summand by pairs again,
$$\frac{x^\rho}{\rho}+\frac{x^{\bar{\rho}}}{\bar{\rho}}=\frac{2x^\beta}{\beta^2+\gamma^2}(\beta\cos(\gamma\log x)+\gamma\sin(\gamma\log x)),$$
we obtain
$$\frac{\psi(x)-x}{\sqrt{x}}=-2\sum_{\gamma>0}\frac{\beta\cos(\gamma\log x)+\gamma\sin(\gamma\log x)}{\beta^2+\gamma^2}+O(1)\tag{2}$$
Now, since $\beta^2<1$ and $\sum_{\gamma}\gamma^{-2}<\infty$ then its not difficult to see that
$$\sum_{\gamma>0}\frac{\beta\cos(\gamma\log x)}{\beta^2+\gamma^2}=O(1),$$
and furthermore that
$$\sum\sin(\gamma\log x)\left(\frac{\gamma}{\beta^2+\gamma^2}-\frac{1}{\gamma}\right)=\sum_{\gamma>0}\sin(\gamma\log x)\left(\frac{-\beta^2}{(\beta^2+\gamma^2)\gamma}\right)=O(1).$$
Substituting into (2) gives
$$\frac{\psi(x)-x}{\sqrt{x}}=-2\sum_{\gamma>0}\frac{\sin(\gamma\log x)}{\gamma}+O(1)=-2\sum_{n\geq 1}\frac{\sin(\gamma_n t)}{\gamma_n}+O(1),$$
where we let $t=\log x$ and the non-trivial zeros are $1/2+\gamma_1,1/2+\gamma_2,\ldots$, where $\gamma_i<\gamma_{i+1}$. This looks curiously like a Fourier series but it is not because $\gamma_i$ are not periodic. Compare with the Fourier series of the Sawtooth function,
$$x-[x]-1/2=-2\sum_{n\geq 1}\frac{\sin(2\pi n x)}{2\pi n},$$
where the fundamental frequencies are $2\pi,4\pi,6\pi,\ldots$. However, the idea is the same where the function is built up over different frequencies. This is the Music of the Primes. The prime counting function is built from the fundamental notes given in the summand. I believe we can do the equivalent of an ``inverse Fourier transform'' and we should get back the prime powers?

\begin{hypothesis}[The Simplicity Hypothesis]
The numbers $\gamma_1,\gamma_2,\gamma_3,\ldots$ are linearly independent over $\mathbb{Q}$.
\end{hypothesis}


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


# The Prime Number Theorem

We will use the notation $f(x)\sim g(x)$ to mean $f(x)/g(x)\longrightarrow 1$ as $x\longrightarrow\infty$, i.e. that $f$ is asymptotic to $g$.

The Prime Number Theorem states that $$\pi(x)\sim\frac{x}{\log x},$$ which tells us that the average spacing between primes around $x$ is $\log(x)$, and the density of primes is $1/\log(x)$.

Let $N(T)$ be the number of zeros in the critical strip to $iT$. Then $$N(T) \sim \frac{T\log T}{2\pi},$$ which implies the average spacing between zeros is $2\pi/\log T$, and the average distance between consecutive complex zeros (in the strip) is $2\pi\log T$. This latter implies the zeros get closer as primes get further apart.

**Proposition.** 
  We have that $$J(x) = \pi(x) + O(x^{1/2}\log x).$$

**Proof.**
  By definition, $$J(x) = \pi(x) + \pi(x^{1/2})/2+\pi(x^{1/3})/3+\cdots = \sum_{k\geq 1}\frac{1}{k}\pi(x^{1/k}),$$ which is a finite sum since eventually $\pi(x^{1/k})=0$ for all $k>n$. Hence,

$$J(x)-\pi(x) = \pi(x^{1/2})/2+\pi(x^{1/3})/3+\cdots+\pi(x^{1/n})/n$$
$$< x^{1/2}/2+\cdots+x^{1/n}/n$$
$$< x^{1/2}/2+\cdots+x^{1/2}/2$$
$$=\frac{(n-1)x^{1/2}}{2},$$

since $\pi(y)<y$ for all $y$. We define $n=\left[\log(x)/\log(2)\right]$, the integer part of the argument. Hence, $$J(x)-\pi(x) = O\left(x^{1/2}\log x\right).$$

**Proposition.** 
  We have that 
  $$\psi(x)\sim x.$$

**Proof.**
  Recall the von-Mangoldt function, $$\psi(x) = x - \sum \frac{x^\rho}{\rho}-\frac{1}{2}\log\left(1-\frac{1}{x^2}\right)-\log(2\pi),$$ where $\zeta(\rho)=0$ are the complex zeros. Dividing by $x$ gives $$\frac{\psi(x)}{x} = 1 - \sum \frac{x^{\rho-1}}{\rho}-\frac{1}{2}\frac{\log\left(1-1/x^2\right)}{x}-\frac{\log(2\pi)}{x}.$$ Clearly the last two terms vanish as $x\longrightarrow\infty$. Now, $\left|x^{\rho-1}\right|=x^{\real{\rho}-1}$, but $\real{\rho}<1$ and so $x^{\rho-1}\longrightarrow 0$ as $x\longrightarrow\infty$. Then, \textit{if the limit can be taken term by term}, then we have that $$\lim_{x\longrightarrow\infty}\sum_\rho\frac{x^{\rho-1}}{\rho}=\sum_{\rho}\lim_{x\longrightarrow\infty}\frac{x^{\rho-1}}{\rho}=0.$$ Therefore, $$\frac{\psi(x)}{x}\longrightarrow 1 as x\longrightarrow\infty,$$ which gives $\psi(x)\sim x$.

This asymptotic result shows that $\psi(x)$ behaves like $x$ as $x\longrightarrow\infty$, which confirms our suspicions from the graph of $\psi(x)$.

**Proposition.** 
  Let $\theta(x) = \sum_{p\leq x} \log p$. Then we have
  $$\theta(x)\sim x.$$

**Proof.**
  We may write the von-Mangoldt function as $$\psi(x) = \theta(x)+\theta(x^{1/2})+\theta(x^{1/3})+\cdots.$$ Now, $$\theta(x^{1/n}) = \sum_{p\leq x^{1/n}}\log p = \sum_{p^n\leq x}\log p,$$ and note that $$\theta(x)>\theta(x^{1/2})>\theta(x^{1/3})>\cdots>\theta(x^{1/n}),$$ where $$n=\left[\frac{\log x}{\log 2}\right].$$ Hence, \begin{eqnarray}\label{ref:eq300} \theta(x)<\psi(x)<\theta(x)+\theta(x^{1/2})\frac{\log x}{\log 2}.\end{eqnarray} Rearranging, $$\psi(x)-\theta(x^{1/2})\frac{\log x}{\log 2}<\theta(x)<\psi(x).$$ Now, since $\psi(x)/x\sim 1$, then $\theta(x)/x\sim 1$ and, for some small $\varepsilon$, $$\frac{\theta(x)}{x^{1+\varepsilon}}=\frac{\psi(x)}{x^{1+\varepsilon}}\longrightarrow 0,$$ as $x\longrightarrow\infty$. Now, dividing (\ref{ref:eq300}) by $x$ gives $$\frac{\psi(x)}{x}-\frac{\theta(x^{1/2})\log x}{x\log 2} < \frac{\theta(x)}{x}<\frac{\psi(x)}{x}.$$ But, the first and last terms tend to $1$ \color{red}and the second term tends to $0$\color{black}, so we conclude that $$\frac{\theta(x)}{x}\longrightarrow 1,$$ as $x\longrightarrow\infty$, which implies $\theta(x)\sim x$, as required.

**Theorem.** 
  $$\pi(x)\sim\frac{\theta(x)}{\log x}\sim\frac{x}{\log x}.$$

**Proof.**
  We have $$\theta(x) = \sum_{p\leq x}\log p \leq \sum_{p\leq x}\log x = \pi(x)\log x.$$ Now let $0<\delta<1$, then

$$\theta(x) \geq \sum_{x^{1-\delta}\leq p\leq x}\log p$$
$$\geq \sum_{x^{1-\delta}\leq p\leq x}(1-\delta)\log x,$$

since, taking logarithms of the range, $\log(x^{1-\delta})=(1-\delta)\log x\leq \log p$. This gives $$\theta(x)\geq (1-\delta)\log(x)(\pi(x)-\pi(x^{1-\delta})).$$ Therefore,

$$\pi(x)\log(x)(1-\delta) \leq (1-\delta)\log(x)\pi(x^{1-\delta})+\theta(x)$$
$$\leq (1-\delta)\log(x)x^{1-\delta}+\theta(x).$$

Dividing by $\theta(x)(1-\delta)$ gives $$\frac{\pi(x)\log x}{\theta(x)}\leq \frac{\log(x)x^{1-\delta}}{\theta(x)}+\frac{1}{1-\delta}.$$ Given $\varepsilon>0$, choose $\varepsilon$ such that $\frac{1}{1-\delta}<1+\frac{\varepsilon}{2}.$ We have
  
  $$\frac{x^{1-\delta}\log x}{\theta(x)} = \frac{x}{\theta(x)}\frac{\log x}{x^\delta}\longrightarrow \frac{\log x}{x^\delta}\longrightarrow 0,$$
  
  as $x\longrightarrow\infty$ (note: $\log(x)/x^\delta\longrightarrow 0$ for $\delta>0$)
  
  Therefore,
  
  $$\color{red}1\leq\color{black} \frac{\pi(x)\log x}{\theta(x)}\leq \frac{\log(x)x^{1-\delta}}{\theta(x)}+\color{red}\frac{1}{\delta-1}\color{black}.$$
  
  Hence, given $\varepsilon>0$, there exists $x_0$ such that RHS$<1+\color{red}\varepsilon\color{black}$. Hence, for $x\geq x_0$, we have $$1\leq \frac{\pi(x)\log x}{\theta(x)}<1+\epsilon,$$ and so $$\frac{\pi(x)\log x}{\theta(x)}\longrightarrow 1,$$
  
  as required.

## Asymptotic Summary
We have
$$\psi(x) \sim x$$
$$\theta(x) \sim x$$
$$\pi(x) \sim \frac{x}{\log x}$$
$$li(x) \sim \frac{x}{\log x}$$
$$J(x) = \pi(x) + O(x^{1/2}\log x)$$
$$\frac{J(x)}{x\log x} = \frac{\pi(x)}{x/\log x} + O\left(\frac{(\log x)^2}{x^{1/2}}\right)\longrightarrow 1$$
$$J(x) \sim \frac{x}{\log x} ~ \pi(x) ~ li(x)$$ 
$$\theta(x) \sim \psi(x) \sim x.$$

# Relation to The Riemann Explicit Formula

**Theorem.** 
Let $p_n$ be the $n^{th}$ prime number. Then $p_n\sim n\log n$.

**Proof.**
  Suppose $y=\pi(x)$, so that $y\sim x/\log x$. Then
  $$
    \frac{y\log x}{x}\longrightarrow 1 as  x\longrightarrow\infty,\tag{eq21}$$
  and so taking logarithms
  $$
    \log y + \log\log x - \log x \longrightarrow 0.
  $$
  Dividing by $\log x$,
  $$
    \frac{\log y}{\log x} + \frac{\log\log x}{\log x} - 1\longrightarrow 0.
  $$
  Since $\log\log x / \log x\longrightarrow 0$ as $x\longrightarrow\infty$, then
  $$
    \frac{\log y}{\log x}\longrightarrow 1.\tag{eq20}
  $$
  Now let $x=p_n$, then
$y=\pi(p_n) = n$, so that on multiplying (eq21) and (eq20) we get
  $$
    \frac{y\log x}{x}\frac{\log y}{\log x}=\frac{y\log y}{x} = \frac{n\log n}{p_n}\longrightarrow 1,
  $$
  as $n\longrightarrow\infty$, so that $p_n\sim n\log n$.

**Note.** that $$J(x)=li(x)+\text{oscillating terms}+\text{bounded terms}.$$ The oscillating terms account for the irregularities in the distribution of the primes.

# Statements Equivalent to the RH

One of the interesting applications of asymptotic analysis of the previous section is that the Riemann Hypothesis may be proven equivalent to certain asymptotic statements. A number of such results will be proven here, as well as some other equivalent statements such as Robin's inequality.

\newpage

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

