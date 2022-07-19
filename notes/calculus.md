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

Derivatives:

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
\frac{d}{dx}c = 0 \\
\frac{d}{dx}x^n = nx^{n-1} \\
\frac{d}{dx}e^x = e^x \\
\frac{d}{dx}\sin x = \cos x \\
\frac{d}{dx}\sec x = \sec x\tan x \\
\frac{d}{dx}\cos x = -\sin x \\
\frac{d}{dx}\csc x = -\csc x\cot x \\
\frac{d}{dx}\tan x = \sec^2 x \\
\frac{d}{dx}\cot x = -\csc^2 x \\
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

Vertices:
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
