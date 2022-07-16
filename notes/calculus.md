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
