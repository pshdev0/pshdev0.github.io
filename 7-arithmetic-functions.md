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
