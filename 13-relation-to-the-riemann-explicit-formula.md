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
