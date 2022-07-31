# Calculus

## Functions and models

- even functions: $f(x) = f(-x)$
- odd functions: $f(-x) = -f(x)$
- polynomials: $f(x) = x^2 + 2x + 1$
- power functions: $f(x) = x^a$
- rational functions: $f(x) = \frac{P(x)}{Q(x)}$ where $P(x)$ and $Q(x)$ are polynomials
- algebraic functions
- transcendental functions: $\sin x \cos x \, e^x \, \ln x$
- exponential functions: $f(x) = b^x$
- logarithmic functions: $f(x) = \log_b x$

Translation:
- up/down: $y = f(x) \pm c$
- right/left: $y = f(x \mp c)$

Stretching:
- vertical: $y = cf(x)$
- horizontal $y = f(c^{-1}x)$

Reflection:
- about the x-axis $y = -f(x)$
- about the y-axis $y = f(-x)$

The composition of two functions:

$$
(f \circ g)(x) = f(g(x))
$$

Note that

$$
f \circ g \ne g \circ f
$$

Inverse functions: reflect about the line $y = x$

Laws of logarithms;

$$
\log_b x^r = r\log_b x
$$

$$
\log_b x + \log_b y = \log_b xy \\
\log_b x - \log_b y = \log_b \frac x y
$$

$$
\log_b x = \frac{\ln x}{\ln b}
$$

## Limits and derivatives

### Limits

$$
\lim_{x \to a} f(x) = L \\
f(x) \to L \text{ as } x \to a
$$

One-sided limits:

$$
\begin{array}{lr}
\lim_{x \to a^+} f(x) = L & \text{right-handed} \\
\lim_{x \to a^-} f(x) = L & \text{left-handed} \\
\end{array}
$$

The Heaviside function:

$$
H(t) =
\begin{cases}
0 & \text{if} & t < 0 \\
1 & \text{if} & t \ge 0
\end{cases}
$$

```{admonition} Strategy: Calculating limits
- try to reduce the number of occurrences of $x$ in $f(x)$
- try to make the expression inside the limit as simple as possible by applying limit laws
- consider using two one-sided limits to determine a limit
```

The precise definition of a limit:

$$
\lim_{x \to a} f(x) = L
$$

if for every number $\varepsilon > 0$ there is a number $\delta > 0$ such that

$$
\text{if} \; 0 < |x - a| < \delta \;\text{then}\; |f(x) - L| < \varepsilon
$$

Continuity:

$f(x)$ is continuous at a number $a$ if

$$
\lim_{x \to a} f(x) = f(a)
$$

```{tip}
$$
\lim_{x \to a} f(g(x)) = \lim_{t \to \lim_{x \to a} g(a)} f(t)
$$
```

````{warning}
Limit laws don't apply to infinite limits!

The following is wrong!!!

```{error}
$$
\lim_{x \to \infty}(x^2 - x) = \lim_{x \to \infty} x^2 - \lim_{x \to \infty} x = \infty - \infty
$$
```
````

### Derivatives

For function

$$
y = f(x)
$$

Its derivative is

$$
f'(x) = y' = \frac{dy}{dx} = \frac{df}{dx} = \frac{d}{dx}f(x) = Df(x) = D_xf(x) \\
= \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

Differentiation rules:

$$
\begin{align*}
    \frac{d}{dx}c & = 0 \\
    \frac{d}{dx}x^n & = nx^{n-1} \\
    \frac{d}{dx}e^x & = e^x \\
    \frac{d}{dx}\sin x & = \cos x \\
    \frac{d}{dx}\cos x & = -\sin x \\
    \frac{d}{dx}\tan x & = \sec^2 x \\
    \frac{d}{dx}\cot x & = -\csc^2 x \\
    \frac{d}{dx}\sec x & = \sec x\tan x \\
    \frac{d}{dx}\csc x & = -\csc x\cot x \\
    \frac{d}{dx}\sin^{-1} x & = \frac{1}{\sqrt{1-x^2}} \\
    \frac{d}{dx}\cos^{-1} x & = -\frac{1}{\sqrt{1-x^2}} \\
    \frac{d}{dx}\tan^{-1} x & = \frac{1}{1+x^2} \\
    \frac{d}{dx}\cot^{-1} x & = -\frac{1}{1+x^2} \\
    \frac{d}{dx}\sinh x & = \cosh x \\
    \frac{d}{dx}\cosh x & = \sinh x \\
\end{align*}
$$

$$
(f \pm g)' = f' \pm g' \\
(fg)' = f'g + fg' \\
\left(\frac{f}{g}\right)' = \frac{f'g - fg'}{g^2}
$$

```{important}
The Chain Rule:

$$
(f \circ g)'(x) = f'(g(x)) \cdot g'(x)
$$

Or alternatively:

$$
\frac{dy}{dx} = \frac{dy}{du}\frac{du}{dx}
$$
```

```{tip}
The Power Rule combined with the Chain Rule:

$$
y = [g(x)]^n = u^n
$$

$$
\frac{dy}{dx} = \frac{dy}{du}\frac{du}{dx} = nu^{n-1}\frac{du}{dx} = n[g(x)]^{n-1}g'(x)
$$
```

The derivative of any exponential function:

$$
\frac{d}{dx}b^x = \frac{d}{dx}(e^{\ln b})^x = \frac{d}{dx}e^{(\ln b)x} = \frac{d}{du}e^u\frac{d}{dx}(\ln b)x = e^{(\ln b) x}\ln b = b^x \ln b
$$

```{tip}
Using the Chain Rule repeatedly:

$$
\frac{dy}{dt} = \frac{dy}{du}\frac{du}{dx}\frac{dx}{dt}
$$

Recursively "peel" the function by differentiating the outmost function evaluated at the inner function and then multiplying the result by the derivative of the inner function.
```

### Implicit differentiation

```{important}
Remember $y$ is a function of $x$
```

````{warning}
Failing to differentiate a constant $c$ and leaving it non-zero is a common error!

```{error}
$$
\begin{align*}
    x^2 - 4xy + y^2 & = 4 \\
    2x - 4y - 4xy' + 2yy' & = 4 \gets \text{this should be 0!}\\
\end{align*}
$$
```
````

### Logarithmic differentiation

$$
\begin{align*}
    \frac{d}{dx}\log_b x & = \frac{1}{x\ln b} \\
    \frac{d}{dx}\ln x & = \frac{1}{x} \\
    \frac{d}{dx}\ln |x| & = \frac{1}{x} \\
\end{align*}
$$

```{admonition} Example
Differentiate

$$
y = \frac{e^{-x}\cos^2x}{x^2 + x + 1}
$$

1. analyze: $e^{-x} > 0$; $\cos^2 x \ge 0$; $x^2 + x + 1 > 0$, therefore $y \ge 0$ and we can take the logarithm without using absolute values
2. take the natural logarithm of both sides:
   
   $$
   \ln y = -x + \ln \cos^2 x - \ln(x^2 + x + 1)
   $$

3. differentiate implicitly with respect to x:
   
   $$
   \frac{1}{y}\frac{dy}{dx} = -1 + \frac{1}{\cos^2 x}[2\cos x\cdot(-\sin x)] - \frac{1}{x^2 + x + 1}(2x + 1)
   $$

4. substitute $y$ with the original function and simplify
   
   $$
   \frac{dy}{dx} = -\frac{e^{-x}\cos^2x}{x^2 + x + 1}(1 + \frac{\sin 2x}{\cos^2 x} + \frac{2x + 1}{x^2 + x + 1})
   $$
```

### Rates of change in physics

Position, velocity and acceleration

Instantaneous velocity is the derivative of the position function with respect to time:

$$
v = \frac{ds}{dt}
$$

Acceleration is the derivative of the velocity function with respect to time:

$$
a = \frac{dv}{dt} = \frac{d^2s}{dt^2}
$$

---

Charge and current

$$
I = \frac{dQ}{dt}
$$

### Exponential growth and decay

Consider the differential equation

$$
\frac{dy}{dt} = ky
$$

It has only one solution:

$$
y(t) = y(0)e^{kt}
$$

This function is extremely common in various sciences.

### Related rates

The essence of relating derivatives with each other is the Chain Rule:

$$
\frac{dy}{dt} = \frac{dy}{dx}\frac{dx}{dt}
$$

Therfore, to relate $dy/dt$ with $dx/dt$, first find an equation that describes the relationship between $y$ and $x$.
Then [differentiate implicitly](#implicit-differentiation) with respect to $t$.

```{warning}
A common error is to forget the minus sign before $dy/dx$ when $x$ is increasing while $y$ is decreasing.
```

```{tip}
When circles are involved, try to use the parametric form (with $r$ and $\theta$) instead of using the classic implcit formula.
```

### Applications of differentiation

Maximum and minimum values

Fermat's theorem
: If $f$ has a local extremum at $c$, and if $f'(c)$ exists, then $f'(c) = 0$.

Critical number
: a number $c$ such that $f'(c) = 0$ or $f'(c)$ doesn't exist

```{admonition} Strategy: The closed interval method
To find the absolute maximum/minimum of a continuous function $f$ on a closed interval $[a, b]$,

1. calculate $f(c)$ for every critical number $c$ on the open interval $(a, b)$
2. calculate the endpoints
```

- The mean value theorem
- Increasing/decreasing test (first derivative)
- The first derivative test
- Concavity test
- Inflection point
- The second derivative test

```{important}
L'Hospital's Rule:

If limit

$$
\lim_{x \to a}\frac{f(x)}{g(x)}
$$

is of the indeterminate form ($\frac{0}{0}$ or $\frac{\infty}{\infty}$), then

$$
\lim_{x \to a}\frac{f(x)}{g(x)} = \lim_{x \to a}\frac{f'(x)}{g'(x)}
$$

provided that $f'(x)$ and $g'(x)$ exist.
```

Curve sketching:

1. Domain
2. Intercepts (if the equation is easy to solve)
3. Symmetry (even/odd) / periodic
4. Asymptotes
   - horizontal: $\lim_{x \to \pm\infty}$
   - vertical: $\lim = \pm\infty$
   - slant: $\lim_{x \to \pm\infty}[f(x)-(mx+b)] = 0$
5. Intervals of increase/decrease
6. Local max/min values
7. Concavity and points of inflection

Newton's method:

$$
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
$$

## Integrals

### The definite and indefinite integrals

$$
\int_a^bf(x)\,dx = \lim_{n \to \infty}\sum_{i=1}^n f(x_i^*)\Delta x
$$

$$
\int f(x)\,dx = F(x)
$$

Table of indefinite integrals:

$$
\begin{align*}
  \int k\,dx & = kx + C \\
  \int x^n\,dx & = \frac{x^{n+1}}{n+1} + C\;(n \ne -1) \\
  \int \frac{1}{x}\,dx & = \ln|x| + C \\
  \int e^x\,dx & = e^x + C \\
  \int b^x\,dx & = \frac{b^x}{\ln b} + C \\
  \int \sin x\,dx & = -\cos x + C \\
  \int \cos x\,dx & = \sin x + C \\
  \int \sec^2 x\,dx & = \tan x + C \\
  \int \csc^2 x\,dx & = -\cot x + C \\
  \int \sec x\tan x\,dx & = \sec x + C \\
  \int \csc x\cot x\,dx & = -\csc x + C \\
  \int \frac{1}{1 + x^2}\,dx & = \tan^{-1} x + C \\
  \int \frac{1}{\sqrt{1-x^2}}\,dx & = \sin^{-1} x + C \\
\end{align*}
$$

Some more exotic ones:

$$
\begin{align*}
  \int \tan x\,dx & = \ln |\sec x| + C \\
  \int \cot x\,dx & = \ln |\sin x| + C \\
  \int \sec x\,dx & = \ln |\sec x + \tan x| + C \\
  \int \csc x\,dx & = \ln |\csc x - \cot x| + C \\
  \int \sinh x\,dx & = \cosh x + C \\
  \int \cosh x\,dx & = \sinh x + C \\
  \int \frac{dx}{x^2 + a^2} & = \frac{1}{a}\tan^{-1}\left(\frac{x}{a}\right) \\
  \int \frac{dx}{\sqrt{a^2 - x^2}} & = \sin^{-1}\left(\frac{x}{a}\right), \;a > 0 \\
  \int \frac{dx}{x^2 - a^2} & = \frac{1}{2a}\ln\left|\frac{x-a}{x+a}\right| \\
  \int \frac{dx}{\sqrt{x^2 \pm a^2}} & = \ln\left|x + \sqrt{x^2 \pm a^2}\right|
\end{align*}
$$

### The FUNDAMENTAL theorem of calculus

Part 1

If

$$
g(x)= \int_a^x f(t)\,dt
$$

then

$$
g'(x) = f(x)
$$

Part 2

$$
\int_a^b f(x)\,dx = F(b) - F(a)
$$

where $F$ is any antiderivative of $f$ ($F' = f$).

```{important}
A few VERY useful trigonometric identities:

Let $u = \tan\frac{x}{2}$, then

$$
\sin x = \frac{2u}{1 + u^2} \;
\csc x = \frac{1 + u^2}{2u}
$$

$$
\cos x = \frac{1 - u^2}{1 + u^2} \;
\sec x = \frac{1 + u^2}{1 - u^2}
$$

$$
\tan x = \frac{2u}{1 - u^2} \;
\cot x = \frac{1 - u^2}{2u}
$$
```

### Integration techniques

This section is **particularly important** because integration is a tricky process and requires a **significant amount** of skill as well as ingenuity.

1. try the formulas given [above](#the-definite-and-indefinite-integrals)
2. simplify the integrand if possible, e.g.
   
   $$
   \int \frac{\tan x}{\sec^2 x}\,dx = \int \sin x\cos x\,dx = \frac{1}{2}\int\sin 2x\,dx
   $$
   
3. try the substitution rule:
   1. look for a part in the expression whose derivative also exists in the integrand
   2. let the part be $u$ where $u = g(x)$
   3. evaluate $du = g'(x)\,dx$
   4. substitue every $x$ in the integrand with appropriate forms of $u$
   5. evaluate the integral $\int f(u)\,du$
   6. If it is an indefinite integral, substitute $x$ back in. Otherwise, replace the limits of integration for $x$ with the corresponding values for $u$.
4. classify the integrand:
   - trigonometric functions:
     - powers of $\sin x$ and $\cos x$, or powers of $\tan x$ and $\sec x$, or powers of $\cot x$ and $\csc x$:
       
       use trigonometric identities to transform the expression and then use the substitution rule
       
     - others:
       
       apply the VERY useful identity above to eliminate everything but $\tan\frac{x}{2}$
     
   - rational functions:
     
     use partial fractions:
     
     1. long division
        
        $$
        f(x) = \frac{P(x)}{Q(x)} = S(x) + \frac{R(x)}{Q(x)}
        $$
        
     2. write $f(x)$ in this way
        
        $$
        f(x) = \sum_{i=1}^m\sum_{u=1}^{u_i}\frac{A_{iu}}{(a_ix + b_i)^u}
             + \sum_{j=1}^n\sum_{v=1}^{v_j}\frac{A_{jv}x + B_{jv}}{(a_jx^2 + b_jx + c_j)^v}
        $$
        
     3. evaluate the transformed integral section by section, completing squares and substituting with $u$ when necessary
     
   - radicals:
     - $\sqrt{\pm x^2 \pm a^2}$:
       
       | Expression       | Substitution                                                                  | Identity                          |
       | ---------------- | ----------------------------------------------------------------------------- | --------------------------------- |
       | $\sqrt{a^2-x^2}$ | $x = a\sin\theta, \;-\pi/2 \le \theta \le \pi/2$                              | $1 - \sin^2\theta = \cos^2\theta$ |
       | $\sqrt{a^2+x^2}$ | $x = a\tan\theta, \;-\pi/2 < \theta < \pi/2$                                  | $1 + \tan^2\theta = \sec^2\theta$ |
       | $\sqrt{x^2-a^2}$ | $x = a\sec\theta, \;0 \le \theta < \pi/2\;\text{or}\;\pi \le \theta < 3\pi/2$ | $\sec^2\theta - 1 = \tan^2\theta$ |
       
     - $\sqrt[n]{ax + b}$:
       
       use substitution $u = \sqrt[n]{ax + b}$
     
   - other:
     
     try integration by parts:
     
     1. separate the integrand into two parts $u$ and $dv$ keeping in mind that $u$ should be as simple as possible while $dv$
        should be easy to integrate
     2. plug everything in:
        
        $$
        \int u\,dv = uv - \int v\,du
        $$

## Differential equations

### First-order ODEs

Separable equations
: Differential equations that can be written in the form

$$
\frac{dy}{dx} = \frac{g(x)}{h(y)}
$$

To solve separable equations,

1. put all of $y$ on one side and all of $x$ on the other side
   
   $$
   h(y)\,dy = g(x)\,dx
   $$
   
2. integrate both sides
   
   $$
   \int h(y)\,dy = \int g(x)\,dx
   $$

Linear equations
: Differential equations that can be put into the form

$$
\frac{dy}{dx} + P(x)y = Q(x)
$$

To solve linear equations,

1. let
   
   $$
   I(x) = e^{\int P(x)\,dx}
   $$
   
2. multiply both sides by $I(x)$
3. transform the left side into a derivative with the product rule
4. integrate both sides

### Second-order ODEs

Second-order linear homogeneous equations
: equations in the form

$$
P(x)\frac{d^2y}{dx^2} + Q(x)\frac{dy}{dx} + R(x)y = 0
$$

If $P(x)$, $Q(x)$ and $R(x)$ are constant-valued functions ($a$, $b$ and $c$), the second-order differential equation
can be easily solved by using auxiliary equations.

Auxiliary equations
: the quadratic equations

$$
ar^2 + br + c = 0
$$

After solving the auxiliary equation, we can get the solution for the original second-order homogeneous linear differential equation
(OMG, that's really a mouthful):

| Roots of the auxiliary equation          | General solution                                    |
| ---------------------------------------- | --------------------------------------------------- |
| $r_1$, $r_2$, real and distinct          | $y = c_1e^{r_1x} + c_2e^{r_2x}$                     |
| $r_1 = r_2 = r$                          | $y = c_1e^{rx} + c_2xe^{rx}$                        |
| $r_1$, $r_2$, complex: $\alpha + i\beta$ | $y = e^{\alpha x}(c_1\cos\beta x + c_2\sin\beta x)$ |

For non-homogeneous linear equations such as

$$
a\frac{d^2y}{dx^2} + b\frac{dy}{dx} + cy = G(x)
$$

it can be proven that the general solution is

$$
y = y_p + y_c
$$

where $y_c$ is the general solution of the complementary homogeneous equation

$$
a\frac{d^2y}{dx^2} + b\frac{dy}{dx} + cy = 0
$$

and $y_p$ is a particular solution of the original equation.

To find a particular solution, use either the method of undetermined coefficients or the method
of variation of parameters.

```{admonition} Method: Undetermined coefficients
1. guess the form of the solution by classifying the function $G(x)$
   
   - $Ce^{kx}\;\to\;Ae^{kx}$
   - a polynomial $P(x)\;\to\;Q(x)$, where $Q(x)$ is a polynomial of the same degree as $P(x)$
   - $C\sin kx \;\text{or}\; C\cos kx\;\to\;A\cos kx + B\sin kx$
   - Everything above can be freely combined or superimposed together.
   - If the guessed form is already a solution of the complementary equation, multiply it by $x$ or $x^2$
   
2. differentiate the function and substitute it into the differential equation
3. solve for the coefficients
```

````{admonition} Method: Variation of parameters
1. replace the constants $c_1$ and $c_2$ in $y_c$ with functions $u_1(x)$ and $u_2(x)$
2. differentiate the altered function $y_p$ and simplify it by imposing conditions
   ```{tip}
   The condition
   
   $$
   u_1'y_1 + u_2'y_2 = 0
   $$
   
   often works well.
   ```
3. plug everything into the original equation and let
   
   $$
   ay'' + by' + cy
   $$
   
   be zero, because $y_1$ and $y_2$ are particular solutions of the complementary equation.
4. solve for $u_1$ and $u_2$
````

If, however, the coefficients of $y$ are not constant-valued functions, some of the second-order ODEs
can still be solved by downgrading them to first-order ODEs.

If the equation is in the form

$$
y'' = f(y, y')
$$

then let $p = y'$. Therefore

$$
y'' = \frac{dp}{dx} = \frac{dp}{dy}\frac{dy}{dx} = p\frac{dp}{dx}
$$

and the original equation turns into a first-order ODE:

$$
p\frac{dp}{dy} = f(y, p)
$$

If the equation is in the form

$$
y'' = f(x, y')
$$

then simply substitute $y'$ with $p$ and integrate $p$ after solving the transformed equation.

## Conic sections

### Parabolas

Parabola, focus, directrix
: The set of points in a plane that are equidistant from a fixed point $F$ (called the **focus**) and a fixed line (called the **directrix**)

Vertex
: The point halfway between the **focus** and the **directrix**

Axis
: The line through the **focus** perpendicular to the **directrix**

An equation of the parabola with focus $(0, p)$ and directrix $y = -p$ is

$$
x^2 = 4py
$$

Or equivalently:

$$
y = \frac{x^2}{4p}
$$


### Ellipses

Ellpise, foci
: An **ellipse** is the set of points in a plane the sum of whose distances from two fixed points $F_1$ and $F_2$ is a constant. The two fixed points are the **foci**.

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 \; (a \ge b)
$$

Vertices
: The points $(a, 0)$ and $(-a, 0)$ in the equation above

Foci:

$$
(\pm c, 0), \text{where}\; c^2 = a^2 - b^2
$$

### Hyperbolas

Hyperbola
: The set of points in a plane the difference of whose distances from two fixed points $F_1$ and $F_2$ is a constant.

The hyperbola

$$
\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1
$$

has foci $(\pm c, 0)$ where $c^2 = a^2 + b^ 2$, vertices $(\pm a, 0)$ and asymptotes $y = \pm(b/a)x$.

### Conic sections in polar forms

Eccentricity $e$, directrix $x = \pm d$

$$
r = \frac{ed}{1 \pm e\cos\theta}
$$

Eccentricity $e$, directrix $y = \pm d$

$$
r = \frac{ed}{1 \mp e\cos\theta}
$$

Specifically, the polar equation of an ellipse with focus at the origin, semimajor axis $a$,
eccentricity $e$, and directrix $x = d$ can be written as:

$$
r = \frac{a(1-e^2)}{1 + e\cos\theta}
$$

In the equation above, the perihelion distance is $a(1 - e)$ and the aphelion distance is $a(1 + e)$.

## Multivariable calculus

TODO

## Vector calculus

TODO
