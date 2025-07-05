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
