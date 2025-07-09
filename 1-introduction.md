# Introduction
## The Fundamental Theorem of Arithmetic
TODO - This is central to the work presented.
## Summation
TODO
## Complex Analysis
### Complex numbers
The set of complex numbers, denoted $\mathbb{C}$, are a generalisation of the real numbers $\mathbb{R}$. We define a complex number $z$ by $z=x+iy$ where $x,y$ are real numbers, e.g. $1$,$-4$,$\pi$,$-3/4$, etc. The symbol $i$ may be treated algebraically like any other symbol with the additional property that $i^2=-1$, i.e. $i=\sqrt{-1}$. We can represent a complex number as the ordered pair $z=(x,y)$ and so imagine it in the "complex plane" as a point. Some notation and facts regarding complex numbers are now given:

- $z^*\equiv\bar{z}\equiv x-iy$
- $\|z\|\equiv\sqrt{z z^*}=\sqrt{(x+iy)(x-iy)}=\sqrt{x^2 - xiy + iyx - i^2 y^2} = \sqrt{x^2 + y^2}$ is the length of the complex number.
- $e^{iz}=\cos z+i\sin z$
- $\Re(z)=x$
- $\Im(z)=y$
- $\text{Arg~}z=\tan_2^{-1}(y/x)$, where $\tan_2$ takes into account the quadrant $z$ belongs to.
- $\log z=\log\|z\|+i(\text{Arg~}(z)+2\pi k)$, where $k\in\mathbb{Z}$.

### Real \& Complex Calculus
Just as with a real function $g$ of a real variable $x$, denoted $g(x)$, we may consider a complex function $f$ of a complex variable $z$, denoted $f(z)$. We may also integrate such functions. Integrating a real function is simple in the sense we can only integrate over intervals of the real line, but complex numbers exist in a two-dimensional plane, so the path of integration can be a two-dimensional curve. We will want to integrate a complex function around a simple closed contour $\gamma$ ("simple" because it does not intersect itself). An example will demonstrate. Suppose we wish to integrate the function $f(z)$ around the contour $\|z\|=1$. We write this as

$$I=\oint_\gamma f(z)dz,$$

where $\gamma = \{ z:\|z\|=1 \}$. The closed contour $\gamma$ may be parametrized by $\gamma = \{ z=e^{i\theta}:0\leq\theta\leq 2\pi \}$, hence

$$I=\int_0^{2\pi}f(e^{i\theta})ie^{i\theta}d\theta,$$

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

so although at $z=z_0$ the function $f$ is not defined (since the denominator would be zero and we can't divide by zero), we can in fact simplify the expression for $f$ and it turns out the function is well-defined at $z=z_0$. (2) a \emph{pole of order $k$} arises for a function whose Laurent series has a finite ``tail'', i.e.

$$\frac{1}{z-z_0}+\frac{2}{(z-z_0)^2}+\cdots+\frac{3}{(z-z_0)^k}.$$

(3) the worst type of singularity is the \emph{essential singularity}, e.g.

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
We write $f=O(g)$ or $f\ll g$ if $\|f(x)\|\leq A\|g(x)\|$ for all $x\geq x_0$ for some $x_0$. We may write $O_\varepsilon(g)$ or $f\ll_\varepsilon g$ if the constant $C$ depends on $\varepsilon$. For example $6x\sin x=O(x)$ or $f(x)=O(1)$ implies that $\|f(x)\|$ is bounded.

By contrast we write $f=o(g)$ if for all $\varepsilon>0$ there exists an $x_0>0$ such that $\|f(x)\|\leq\varepsilon A\|g(x)\|$ for all $x\geq x_0$ for some $x_0$ which loosely speaking means that $f$ is \emph{strictly} bounded by $g$.

## The Mellin Transform
The Mellin transform

$$\mathcal{M}[f](s) = \int_0^\infty x^{s-1}f(x) dx,$$

or

$$\mathcal{M}_1[f](s) = \int_{1}^{\infty}x^{-s-1}f(x)dx$$

is an integral transform such that $\mathbb{R}\rightarrow\mathbb{C}$. We have the following basic properties:

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

- "Mellin" formula

$$\int_0^\infty x^{s/2-1}e^{-n^2\pi x}dx=\mathcal{M}\left[\sum_{k=0}^\infty\frac{(n^2\pi)^k}{k!}(-x)^k\right](s/2)\stackrel{RMT}{=}\frac{\Gamma(s/2)}{n^s\pi^{s/2}}.$$

- Stirling-Laplace asymptotic formula: $\Gamma(z)\sim \sqrt{2\pi}z^{z-1/2}e^{-z}$.

Our first theorem may seem a little esoteric and abstract, but bear with it as it's the "worst" it will get!

**Theorem.** (Hadamard's Factorization Theorem)
Let $f$ be an entire function of finite order $\omega$ and $z_i$ the non-zero zeros of $f$ with multiplicity. Let 0 be a zero of $f$ with multiplicity $m$. Let the \emph{rank} of $f$, $p<\omega$, be the smallest integer $p$ such that
$\sum_{n=1}^\infty1/\|z_n\|^{p+1}<\infty$. Then there exists a polynomial $g$ whose degree is at most $\omega$ such that
$$f(z)=z^me^{g(z)}\prod_{n=1}^\infty E_p(z/z_n),$$
where $E_p$ is the $p$-th Weierstrass elementary factor, $E_0=1-z$ and $E_p=\exp(z+z^2/2+\cdots+z^p/p)$.


**Proposition.** 
Let $\Re s\geq\delta>0$, then by Stirling-Laplace,

$$\left\|\frac{1}{\Gamma(s)}\right\|\sim\frac{1}{\sqrt{2\pi}}\left\|s^{1/2-s}e^{s}\right\|=\frac{1}{\sqrt{2\pi}}\left\|e^{-(s-1/2)\log s+s}\right\|=\frac{1}{2\pi}\left\|e^{-(\sigma-1/2)\log\|s\|+t\theta+\sigma}\right\|.$$

We will show that

$$e^{-(\sigma-1/2)\log\|s\|+t\theta+\sigma}<Ce^{\|s\|^{1+\varepsilon}}\equiv e^{c+\|s\|^{1+\varepsilon}},$$

or equivalently $\color{ForestGreen}-(\sigma-1/2)\log\|s\|\color{black}+\color{NavyBlue}t\theta+\sigma\color{black}<c+\color{RedOrange}\|s\|^{1+\varepsilon}$ for some constant $c>0$ and $x\equiv\|s\|$ sufficiently large. Since $x>\sigma,t$ and $\|\theta\|\leq\pi/2$ then wlog we may rewrite

$$\color{ForestGreen}(x+1/2)\log(x)\color{black}+\color{NavyBlue}(\pi/2+1)x\color{black}-\color{RedOrange}x^{1+\varepsilon}\color{black}=x\log(x)-x^{1+\varepsilon}+O(x)\to-\infty,$$

as $x\to\infty$ since $\lim_{x\to\infty}(x\log x)/x^{1+\varepsilon}=0$. Therefore, the right hand side is bounded above and $\Gamma^{-1}(s)\ll_\varepsilon e^{\|s\|^{1+\varepsilon}}$. Now using Euler's reflection formula and similar reasoning,

$$\left\|\frac{1}{\Gamma(1-s)}\right\|=\color{ForestGreen}\left\|\Gamma(s)\right\|\color{NavyBlue}\left\|\frac{\sin(\pi s)}{\pi}\right\|\color{black}\ll_{\varepsilon}\color{ForestGreen}e^{\|s\|^{1+\varepsilon}}\color{NavyBlue}e^{\pi\|s\|}\color{black}\ll_{\varepsilon} e^{\|s\|^{\varepsilon+1}}.$$

Therefore, since $\Gamma^{-1}(s)$ is an entire function with zeros at the non-positive integers then by Hadamard's factorisation theorem,

$$\frac{1}{\Gamma(s)}=e^{a+bs}s\prod_{n=1}^\infty\left(1+\frac{s}{n}\right)e^{-s/n}.$$
