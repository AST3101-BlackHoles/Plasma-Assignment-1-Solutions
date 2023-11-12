# Plasma Assignment 1

  * 25% of final grade
  * assigned 27 Oct 2023
  * due 3 Nov 2023

---

## Problem 1

> Compute the trajectory for ballistic motion in the Rindler metric.
> 
> ```math
> ds^2 = - (ax)^2 dt^2 + dx^2
> ```

The Rindler coordinates are isomorphic with Minkowski under the coordinate change (with `c=1`)

```math
T = x \sinh (at)
```
```math
X = x \cosh (at)
```

which means

```math
t = \frac{1}{a} \tanh^{-1} (T/X)
```
```math
x = \sqrt{X^2 - T^2}
```

In Minkowski, ballistic motion is simple

```math
X = X_0 + \beta T
```

and therefore we can express motion in the Rindler coordinates as

```math
t = \frac{1}{a} \tanh^{-1} ( T / (X_0 + \beta T))
```
```math
x = \sqrt{X_0^2 + 2 X_0 \beta T + \beta^2 T^2 - T^2}
```

## Problem 2

> Compare the orbital energy of a point particile in a circular orbits for Newtonian gravity and the Schwarzschild metric.
> Which has a larger rate of change with the orbital radius?
> How would this impact the evolution of a compact binary coalescence?

In Newtonian Gravity, we have

```math
V_\mathrm{eff} = - \frac{GM}{r} + \frac{L^2}{2r^2}
```

with the interpreation that `L` is the angular momentum per unit mass. Minimizing this with respect to `r` yields

```math
L^2 = GM r
```

and therefore

```math
E_\mathrm{orb} = V_\mathrm{eff}(r) = - \frac{GM}{2r}
```

For time-like orbiats in Schwarzschild, we have

```math
V_\mathrm{eff} = \frac{1}{2} - \frac{GM}{r} + \frac{L^2}{2r^2} - \frac{GML^2}{r^3}
```

Minimizing this with respect to `r` yields

```math
L^2 = r^2 \left( \frac{GM}{r - 3GM} \right)
```

and therefore

```math
E_\mathrm{orb} = \left(\frac{1}{2} - \frac{GM}{r} \right) \left( 1 + \frac{GM}{r-3GM} \right)
```

If we differentiate these with respect to `r`, we find

```math
\frac{dE_\mathrm{New}}{dr} = \frac{GM}{2r^2} \leq \frac{dE_\mathrm{Sch}}{dr}
```

In the limit of large orbital separations (`r >> 6GM`), we have

```math
\frac{dE_\mathrm{Sch}}{dr} = \frac{dE_\mathrm{New}}{dr} \left( 1 + \frac{6GM}{r} \right)
```

The basic Post-Newtonian energy balance equation reads

```math
\frac{dE_\mathrm{orb}}{dr} \frac{dr}{dt} = - \mathcal{L}_\mathrm{GW}(r)
```

so that the radius will evolve more slowly if dE/dr is larger. This means that relativistic corrections to the orbital binding energy tend to slow down the evolution of the orbit at first order (compared to the Newtonian binding energy).
