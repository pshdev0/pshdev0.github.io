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
