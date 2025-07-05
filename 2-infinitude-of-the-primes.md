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