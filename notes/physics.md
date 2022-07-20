# Physics

## Motion

In an $O-xyz$ coordinate system the position vector $\vec r$ is defined as:

$$
\vec r(t) = x(t)\hat i + y(t)\hat j + z(t)\hat k
$$

Its magnitude is:

$$
r(t) = \sqrt{x^2 + y^2 + z^2}
$$

In polar coordinates, it is usually defined in terms of $r$ and $\theta$.

The displacement vector $\Delta\vec s$ is defined as:

$$
\Delta\vec s = \vec r(t + \Delta t) - \vec r(t)
$$

The average velocity is:

$$
\bar{\vec v} = \frac{\Delta\vec s}{\Delta t}
$$

The instantaneous velocity and acceleration is:

$$
\vec v = \lim_{\Delta t \to 0} \frac{\Delta\vec s}{\Delta t} = \frac{d\vec s}{dt} \\
\vec a = \frac{d\vec v}{dt}
$$

Formulas for constant acceleration motion on a straight line:

$$
\begin{align*}
  v & = v_0 + at \\
  S & = v_0t + \frac 1 2 at^2 \\
  v^2 - v_0^2 & = 2aS \\
  S & = \frac 1 2 (v_0 + v)t
\end{align*}
$$

```{admonition} Strategy: Maximum/minimum values
1. write down the expression for the variable
2. simplify the expression so that it contains one and **only one** **independent** variable
3. mathematically determine the extremum
```

```{admonition} Alternative strategy: Maximum/minimum values
This is best suited for geometric problems (instead of ones that requires tons of calculation).
1. try to determine the position of extremum by *intuition* (sort of obscure)
2. rigorously prove your *intuition*
3. solve the problem
```

### Falling objects

```{admonition} Model: Falling objects with initial upward velocity
$$
\left\{
\begin{array}{l}
    x = v_0 \cos\theta\,t \\
    y = v_0 \sin\theta\,t - \frac{1}{2}gt^2
\end{array}
\right.
$$

$$
\left\{
\begin{array}{l}
    v_x = v_0\cos\theta \\
    v_y = v_0\sin\theta - gt
\end{array}
\right.
$$
```

```{admonition} Model: Objects falling onto a tilted surface
1. create a coordinate system with the surface as the x(y)-axis
2. identify the initial conditions (velocity, position and acceleration)
3. plug in the equations and solve the problem
```

### Circular and spiral motion

Rigid bodies:

- translational motion
- rotational motion
- combination motion

Angular velocity

$$
\omega = \lim_{\Delta t \to 0} \frac{\Delta \theta}{\Delta t} = \frac{d\theta}{dt}
$$

Angular acceleration

$$
\beta = \frac{d\omega}{dt}
$$


Constant-angular-acceleration rotational motion:

$$
\begin{align*}
  \omega & = \omega_0 + \beta t \\
  \theta & = \omega_0 t + \frac{1}{2}\beta t^2 \\
  \omega^2 - \omega_0^2 & = 2\beta\theta \\
  \theta & = \frac{1}{2}(\omega_0 + \omega)t
\end{align*}
$$

The radius of curvature $\rho$:

$$
\rho = \left|\frac{(1 + y'^2)^{3/2}}{y''}\right|
$$

```{tip}
The acceleration of an object stays the same in different inertial reference frames.
```

````{tip}
Switching inertial reference frames is an excellent way to calculate acceleration.

```{admonition} Example
$$
a = \frac{v^2}{r}
$$

if the center of rotation is stationary in a particular reference frame
```
````

```{admonition} Strategy: Problems involving the angle between two vector quantities
Express the vector (for example, velocity or acceleration) by selecting a pair of basis vectors and then utilizing the [dot product](linear-algebra.md#dot-products-and-lengths):

$$
\cos\theta = \frac{\vec{u}\cdot\vec{v}}{\Vert\vec{u}\Vert\Vert\vec{v}\Vert}
$$

Or more specifically, when $\vec{u}\perp\vec{v}$,

$$
\vec{u}\cdot\vec{v} = 0
$$
```

```{note}
A reference frame can be rotating, in which case it is called a rotating reference frame. A
rotating reference frame is **not** an inertial reference frame.

If a **rotating object** seems to be **stationary** in a rotating reference frame, then it has the same
angular speed as the rotating frame itself, although the direction of $\omega$ (angular velocity)
is reversed.

$$
\omega_{object} = -\omega_{frame}
$$
```

## The balance of objects

### The balance of forces

Types of forces:

- gravitational force
- elastic force
- friction
- $\dots$

Springs:

$$
\vec{F} = -k\Delta\vec{x}
$$

where $k$ is the spring constant.

Multiple springs:

- series:
  
  $$
  \frac{1}{k} = \frac{1}{k_1} + \frac{1}{k_2} + \cdots
  $$
- parallel:
  
  $$
  k = k_1 + k_2 + \cdots
  $$

Friction angle:

let $\mu = \tan\varphi$, then

$$
\frac{f_{max}}{N} = \mu_{static} = \tan\varphi
$$

Generally, $f_{static} < f_{max}$. Therefore, 

$$
f_{static} < \mu_{static}N \\
\frac{f_{static}}{N} < \mu_{static} = \tan\varphi
$$

The angle $\alpha$ between the full reaction force $F$ and the normal line cannot be greater than the friction angle $\varphi$

$$
\alpha = \arctan\frac{f_{static}}{N} < \varphi
$$

```{attention}
When the solution to a problem can not be specified as a fixed value, solve for the range of values it lies in.
```

```{admonition} Strategy: Balancing objects influenced by friction
1. use "friction angles"
   
   $$
   \tan\varphi = \mu
   $$
   
2. use geometry and trigonometry to figure out the relationship between the angles
3. substitute $\mu$ back in and get the answer
```

```{admonition} Strategy: The fewer forces, the better
When a large object is in balance, try to find a segment of the object on which the fewest forces act.
In other words, restrict yourself to one or two forces.
```

### Moment and rotation

```{admonition} Model: An object with a hole in it
1. pretend that the hole doesn't exist
2. recreate the hole by putting a force in the opposite direction
```

```{tip}
If the direction of a force is unknown, suppose it is in a specific direction and determine whether the system
can stay in balance.

Alternatively, use a coordinate system, write down the force as a general vector $x\hat i + y\hat j + z\hat k$
and apply [linear algebra](linear-algebra.md#linear-algebra)
```

```{admonition} Model: Steelyard balance
![A steelyard balance](_static/19th-century_steelyard.png)

(By An Elementary Treatise on Analytic Mechanics: With Numerous Examples By Edward A. (Edward Albert) Bowser, 1893., Public Domain, [Link](https://commons.wikimedia.org/w/index.php?curid=1319572))

Let $|AC| = d$, $|CO| = l_0$, and let $M$ be the moment the gravity of the whole balance has on the pivot $C$

Then if the mass of the weight is $m$, and the mass of the counterweight is $m_0$, we have

$$
M = m_0gl_0
$$

and

$$
mgd + M = m_0g(l_0 + \lambda m)
$$

where $\lambda$ is the ratio of the distance between $O$ and the counterweight and $m$.

Therefore,

$$
d = \lambda m_0
$$

This is the fundamental equation of steelyard balances.
```
