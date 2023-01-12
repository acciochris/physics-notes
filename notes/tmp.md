# Temporary notes

> Note:
> 
> Notes taken here will eventually be moved to other places.

## Curve length integral

$$
L = \int_a^b \sqrt{1 + \left(\frac{dy}{dx}\right)^2}\,dx
$$

## Speed of waves in fluids

Continuity equation:

$$
\begin{align}
  (\rho u)_x & = -\rho_t \\
  \rho_x u + \rho u_x & = -\rho_t \\
  \rho u_x & = -\rho_t \\
  \rho u_{xx} & = -\rho_{tx} = -\rho_{xt}
\end{align}
$$

Pressure:

$$
\begin{align}
  p_x & = -(\rho u)_t \\
  \frac{\partial p}{\partial \rho} \rho_x & = -\rho_t u - \rho u_t = -\rho u_t \\
  \frac{\partial p}{\partial \rho} \rho_{xt} & = -\rho_t u_t - \rho u_{tt} = -\rho u_{tt} \\
\end{align}
$$

Combining $(4)$ and $(7)$,

$$
\begin{align}
  u_{tt} & = \frac{\partial p}{\partial \rho} u_{xx} \\
  c & = \sqrt{\frac{\partial p}{\partial \rho}} \\
\end{align}
$$

## Oscillations

Simple harmonic motion:

$$
A = \sqrt{x_0^2 + \left(\frac{v_0}{\omega}\right)^2}
$$

where $x_0$ and $v_0$ are the initial displacement and velocity, respectively.

```{caution}
Be careful with the signs of $x_0$ and $v_0$!!!
```

For the phase, draw a circle of trigonometry and be careful with the domain of the $\arcsin x$ and
$\arccos x$ functions.
