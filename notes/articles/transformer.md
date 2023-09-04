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
Mutual Inductance:

$$
\newcommand{\V}[1]{\mathbf{#1}}
M = \frac{\Psi_1}{I_2} = \frac{\int\V{B}_2\cdot d\V{a}}{I_2} = \int\left(\frac{\mu_0}{4\pi}\int\frac{Id\V{l}\times\V{\hat r}}{r^2}\right)\cdot d\V{a}\;I_2^{-1}
$$
```

