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

## Satellite Orbits and Binet Equation

### Part I: integrating orbital motion

As

$$
\begin{align*}
  E & = \frac{L^2}{2mr^2} + \frac{1}{2}m\dot{r}^2 - \frac{GMm}{r} \\
  \frac{dr}{d\theta} & = \frac{\dot{r}}{\dot{\theta}} \\
  L & = mr^2\dot{\theta} \\
\end{align*}
$$

If we eliminate $\dot{\theta}$ and $\dot{r}$, and let $u = \dfrac{1}{r}$, then

$$
\begin{align*}
  du & = -\sqrt{\frac{2mE}{L^2} + \frac{2GMm^2}{L^2}u - u^2}\;d\theta \\
  & = -\sqrt{A^2 - (u - B)^2}\;d\theta
\end{align*}
$$

where $A = \sqrt{\dfrac{2mE}{L^2} + B^2}$ and $B = \dfrac{GMm^2}{L^2}$

Substitute $u = Au' + B$, then

$$
\begin{align*}
  \int - \frac{du'}{\sqrt{1-u'^2}} & = \int d\theta \\
  \arccos \frac{u - B}{A} & = \theta - \theta_0 \\
  r & = \frac{B^{-1}}{1 + \frac{A}{B}\cos(\theta - \theta_0)} \\
\end{align*}
$$

Thus semi-latus rectum

$$
l = B^{-1} = \frac{L^2}{GMm^2} = \frac{b^2}{a}
$$

and eccentricity

$$
e = \frac{A}{B} = \sqrt{1 + \frac{2EL^2}{G^2M^2m^3}}
$$

### Part II: Binet equation

$$
E = \frac{L^2}{2m}u^2 + \frac{1}{2}m\left(\frac{d}{dt}\frac{1}{u}\right)^2 + V(r)
$$

where

$$
\frac{d}{dt}\frac{1}{u} = \frac{d}{du}\left(\frac{1}{u}\right)\frac{du}{d\theta}\frac{d\theta}{dt} = -\frac{1}{u^2}u'\frac{L}{m}u^2 = -\frac{L}{m}u'
$$

According to the conservation of energy

$$
\begin{align*}
  \frac{dE}{du} & = \frac{L^2}{2m}\left(2u + \frac{d(u'^2)}{d\theta}\frac{d\theta}{du}\right) + \frac{d}{dr}V(r)\frac{dr}{du} \\
  & = \frac{L^2}{m}(u + u'') + \frac{F(u^{-1})}{u^2} \\
  & = 0
\end{align*}
$$

Thus we have Binet equation

$$
\frac{L^2}{m}(u + u'') + \frac{F(u^{-1})}{u^2} = 0
$$

## Multi-variable linear recurrence relations

Suppose matrix $A$ has eigenvalue matrix $\Lambda$ and eigenvector matrix $X$, then

$$
\begin{align*}
  \vec{v}_{n+1} & = A\vec{v}_n + \vec{b} \\
  X^{-1}\vec{v}_{n+1} & = X^{-1}A\vec{v}_n + X^{-1}\vec{b} \\
                      & = \Lambda X^{-1}\vec{v}_n + X^{-1}\vec{b} \\
\end{align*}
$$

Let $X^{-1}\vec{v}_n = \vec{v}'_n$ and $X^{-1}\vec{b} = \vec{b}'$, then

$$
\vec{v}'_{n+1} = \Lambda\vec{v}'_n + \vec{b}'
$$

is a recurrence relation that can be solved one by one.

Finally,

$$
\vec{v}_n = X\vec{v}'_n
$$

## Second derivative test of multi-variable functions

If

$$
f_x(a, b) = f_y(a, b) = 0
$$

then

- local maximum at $(a, b)$ if $f_{xx} < 0$ and $f_{xx}f_{yy} - f_{xy}^2 > 0$
- local minimum at $(a, b)$ if $f_{xx} > 0$ and $f_{xx}f_{yy} - f_{xy}^2 > 0$
- local saddle at $(a, b)$ if $f_{xx}f_{yy} - f_{xy}^2 < 0$
- inconclusive if $f_{xx}f_{yy} - f_{xy}^2 = 0$
