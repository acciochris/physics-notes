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

## Collisions

$$
v_1' = \frac{(m_1 - m_2)v_1 + 2m_2v_2}{m_1 + m_2}
$$

For $v_2'$, simply replace $1$ with $2$ and $2$ with $1$.

## Solid Angles

$$
d\Omega = \sin\theta\,d\theta\,d\phi
$$

A solid angle with apex angle $2\theta$

$$
\Omega = \int\sin\theta\,d\theta\,d\phi = \int_0^{2\pi}d\phi \int_0^\theta\sin\theta\,d\theta = 2\pi(1-\cos\theta) = 4\pi\sin^2\frac{\theta}{2}
$$

## Envelope of a family of curves

Assume every curve of the family is an implicitly defined function $f_t(x, y) = 0$ where $t$ is the
parameter. Let

$$
F(t, x, y) = f_t(x, y)
$$

Then the envelope is the collection of points $(x, y)$ satisfying

$$
F(t, x, y) = 0\;\;\text{and}\;\;\frac{\partial F(t, x, y)}{\partial t} = 0 
$$

## Circles in polar coordinates

$$
\begin{align*}
  (x - a)^2 + (y - b)^2 & = R^2 \\
  (r\cos{\theta} - a)^2 + (r\sin{\theta} - b)^2 & = R^2 \\
  r^2 - (2a\cos{\theta} + 2b\sin{\theta})r + a^2 + b^2 - R^2 & = 0 \\
\end{align*}
$$
