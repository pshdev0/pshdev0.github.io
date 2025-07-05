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

**Hypothesis. (The Simplicity Hypothesis)** The numbers $\gamma_1,\gamma_2,\gamma_3,\ldots$ are linearly independent over $\mathbb{Q}$.
