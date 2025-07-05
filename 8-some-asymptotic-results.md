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
