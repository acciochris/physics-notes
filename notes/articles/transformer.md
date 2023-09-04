# Transformers

![transformer](../images/transformer.svg)

## Step 1: determine positive direction for currents

1. select a positive direction for magnetic flux
2. the positive direction for currents is the direction in which the flux produced will be positive

## Step 2

1. let the flux in the iron core be $\Phi$
2. write down the equations of electromagnetic induction

$$
\newcommand{\emf}{\mathcal{E}}
\begin{align*}
    \emf_1 & = -\frac{d\Phi_1}{dt} = -N_1\frac{d\Phi}{dt} \\
    \emf_2 & = -\frac{d\Phi_2}{dt} = -N_2\frac{d\Phi}{dt} \\
\end{align*}
$$

According to [my last article on circuits](./circuits.md),

$$
\newcommand{\emf}{\mathcal{E}}
\begin{align*}
    U_1 & = -\emf_1 = N_1\frac{d\Phi}{dt} \\
    U_2 & = -\emf_2 = N_2\frac{d\Phi}{dt} \\
\end{align*}
$$

And this is where textbooks usually end. (except perhaps with another equation for COE)

$$
U_1I_1 = U_2I_2
$$

## Step 3: dive deeper

Let $L_i$ be the self-inductance of the $i$th coil, and $M$ be the mutual inductance.

Then

$$
\begin{align*}
    \Phi_1 = L_1I_1 + MI_2 \\
    \Phi_2 = L_2I_2 + MI_1 \\
\end{align*}
$$

Thus 

$$
\begin{align*}
    U_1 & = L_1\frac{dI_1}{dt} + M\frac{dI_2}{dt} \\
    U_2 & = L_2\frac{dI_2}{dt} + M\frac{dI_1}{dt} \\
\end{align*}
$$

```{note}
Mutual Inductance reciprocity theorem:

$$
\newcommand{\V}[1]{\mathbf{#1}}
M = \frac{\Psi_1}{I_2} = \frac{1}{I_2}\int\V{B}_2\cdot d\V{a}_1 = \frac{1}{I_2}\int\V{A}_2\cdot d\V{l}_1 = \frac{1}{I_2}\int\left(\frac{\mu_0}{4\pi}\int\frac{I_2d\V{l_2}}{r}\right)\cdot d\V{l}_1 = \frac{\mu_0}{4\pi}\iint\frac{d\V{l}_1 \cdot d\V{l}_2}{r}
$$

$$
M = \frac{\Psi_1}{I_2} = \frac{\Psi_2}{I_1}
$$
```

Solving for $\dot{I}_1$ and $\dot{I}_2$, we get

$$
\begin{align*}
    \dot{I}_1 &= \frac{U_2L_1 - U_1M}{L_1L_2 - M^2} \\
    \dot{I}_2 &= \frac{U_1L_2 - U_2M}{L_1L_2 - M^2} \\
\end{align*}
$$

Switching to complex numbers[^1] (by assuming a sinusoidal signal), we get

$$
\begin{align*}
    j\omega\tilde{I}_{10} &= \frac{\tilde{U}_{20}L_1 - \tilde{U}_{10}M}{L_1L_2 - M^2} \\
    j\omega\tilde{I}_{20} &= \frac{\tilde{U}_{10}L_2 - \tilde{U}_{20}M}{L_1L_2 - M^2} \\
\end{align*}
$$

Below is a visualization of the four voltages and currents in Geogebra. ([unembedded version](https://www.geogebra.org/calculator/hcamnfjm))

<iframe src="https://www.geogebra.org/calculator/hcamnfjm?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

## Step 4: Power

You may have noticed that there are two additional points on the graph. They are the complex powers.

Derivation:

For

$$
\begin{align*}
    U &= U_0\cos(\omega t + \varphi_{U}) \\
    I &= I_0\cos(\omega t + \varphi_{I}) \\
\end{align*}
$$

Power

$$
P = UI = U_0I_0\cos(\omega t + \varphi_{U})\cos(\omega t + \varphi_{I}) \\
= U_0I_0\frac{1}{2}\left(\cos(2\omega t + \varphi_{U} + \varphi_{I}) + \cos(\varphi_{U} - \varphi_{I})\right)
$$

The first term is sinusoidal and averages to zero. It's called reactive power.
The second term does not average to zero and is the real power.

In complex form:

$$
S_0 = S = \frac{1}{2}\tilde{U}\tilde{I}^* = \frac{1}{2}\tilde{U}_0\tilde{I}_0^* = P_0 + jQ_0
$$

where the real part is the real power and the complex part is the reactive power.

[^1]: We can always do so because $\Re(x)' = \Re(x')$
