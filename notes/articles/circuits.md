# Circuits

Circuits are an important subfield in the science of electromagnetism, where batteries, wires,
resistors, capacitors, inductors, and of course diodes play important roles. However, after studying
circuits carefully, I seem to have discovered something that textbooks gloss over, but is crucial to
understanding the fundamentals of circuits, especially complex ones. Hopefully, I have not made a
terrible mistake.

## Current

When a wire is connected to the two terminals of a battery (never do this at home, kids), current will
flow in the wire.

However, for the charge carriers (electrons) to start moving, we must first establish an electromagnetic
field. When the fields are established, a **steady current** forms in the wire. In fact, the fields are
also responsible for maintaining the current, so that it remains the same everywhere along the wires.
Otherwise, charge would be piling up somewhere in the circuit. To be exact, as soon as charge begins to
pile up, the Coulumb forces between the individual electrons force them apart, smoothing out the current.

Therefore, when analyzing circuits, a rule of thumb is to assume steady current everywhere, even in
AC circuits since EM fields establish themselves so quickly. (forget about capacitor plates, for now)

## Electromotive force

The source of an emf can be a battery, or a changing magnetic field (or even by manually pushing charges
along), as long as work is done on the charges. The emf can be defined to be the *work done per unit charge*
by a source.

$$
\mathcal{E} = \frac{W}{q} = \int_{\mathcal{P}} \mathbf{f}_s\cdot d\mathbf{l}
$$

where $\mathbf{f}_s$ is the force per unit charge and $\mathcal{P}$ is *the path along the source*.

```{note}
There can be some subtleties, for example motional emfs. Magnetic forces indeed do no work, however, the
force pulling on the wire does. So there is work done per unit charge.
```

## Resistance

Resistance is often defined as

$$
R = \frac{\Delta V}{I}
$$

so that we would often say the potential difference between the two terminals of a resistor

$$
\Delta V = IR
$$

However, consider the case where a solenoid is placed in a circular ring of wire and where the solenoid
produces a changing magnetic field.

![Circular ring](../images/circuit-magnetic-field.svg)

Since this is perfectly symmetric, will there be any potential difference? Since

$$
\nabla\times\mathbf{E} = -\frac{\partial\mathbf{B}}{\partial t}\neq 0
$$

will there be any potential?

Therefore resistance would be better defined by the equation for resistivity

$$
\mathbf{J} = \frac{1}{\rho}\mathbf{f}
$$

where $\mathbf{f}$ if the force per unit charge, and

$$
R = \rho\frac{L}{A}
$$

As to the original question, let us consider the energy of the individual electrons:

1. The kinetic energy of electrons can be safely ignored, since $m_e$ is so tiny.
2. As a result of 1., the other forms of energy, namely electro***static*** energy, heat, and work done by the
   $\nabla\times\mathbf{E} = -\dfrac{\partial\mathbf{B}}{\partial t}$ field must transform into one another.
3. In the original question, the work done by the curly $\mathbf{E}$ field perfectly transforms into heat,
   so there is no potential difference anywhere.

## Inductors and Capacitors

When it comes to inductors and capacitors, we need to view circuits from another perspective, so as to
reduce our cognitive load. What we need, once again, is the aid of *energy*, but in a *macroscopic* manner.

Consider this simple RLC circuit.

![RLC Circuit](../images/circuit.svg)

```{important}
When considering a circuit, it is important to give everything a sign, a sign as intuitive and as
straightforward as possible. In this case, we will choose clockwise as the positive direction for currents
and select the left terminal of the capacitor and the AC source to be the positive terminal.
```

When current flows in the clockwise direction, the charge on the capacitor increases, implying the fact
that the capacitor is gaining energy from the currunt, thus requiring the former to impede the flow
of the latter, establishing a potential difference across the capacitor.

Similarly, the inductor gains *magnetic* energy as the currunt increases, meaning the emf it induces
must be in the opposite direction of the current. Taking into account the energy of electrons
(see [Resistance](#resistance)), the corresponding electro***static*** field must be in the same direction
as the current.

Thus we write (following clockwise around the circuit, considering whether the individual components encourage or oppose the current)

$$
u - iR - \frac{q}{C} - L\frac{di}{dt} = 0
$$

As $\dot{q} = i$, this can further be transformed into

$$
\frac{1}{C}q + R\dot{q} + L\ddot{q} = u
$$

Assuming

$$
u = \tilde{u} = \tilde{u}_0e^{j\omega t}
$$

and

$$
\dot{q} = \tilde{i} = \tilde{i}_0e^{j\omega t}
$$

we have

$$
(\frac{1}{j\omega C} + R + j\omega L)\tilde{i}_0 = \tilde{u}_0
$$

(which is basically *the* most important equation to note in AC circuits, showing the impedances of capacitors,
resistors and inductors)

## Voltmeters

```{warning}
The following is one of *the* most crazy inventions by teachers!!!
```

You should definitly avoid putting voltmeters in strange circuits, *especially* those in which curly $\mathbf{E}$ fields are involved. But they do appear in exams :-(

First things first, what on earth do voltmeters measure???

*Answer*: Surprise! It does not measure the potential difference across its two terminals, since the potential
itself is ill-defined when $\nabla\times\mathbf{E} \neq 0$. Instead, it measures

$$
\int\mathbf{E}\cdot d\mathbf{r}
$$

And that's it. Whenever crazy questions appear, try your best to determine this integral.
