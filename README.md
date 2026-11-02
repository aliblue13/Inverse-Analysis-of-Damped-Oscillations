# Inverse Analysis of Damped Oscillations

Mini project for **Differential Equations** (Spring/2024), Ferdowsi University of Mashhad.
**Author:** Ali Bolourian | **Instructor:** Dr. Reza Khajavi

An interactive Mathematica notebook that (1) solves the damped harmonic oscillator and (2) recovers its parameters from displacement data by curve fitting (an inverse problem).

## Part 1: Forward problem

The mass-spring system with damping is modeled as

```
x''(t) + γ x'(t) + ω x(t) = 0,   x(0) = A,  x'(0) = 0
```

where γ = b/m is the damping coefficient and ω = k/m (the square of the natural angular frequency).

- `DSolve` gives the general solution symbolically.
- The undamped case (γ = 0) reduces to simple harmonic motion, x(t) = A cos(t) for ω = 1.
- `Manipulate` sliders for A, γ and ω show how the motion changes.

## Part 2: Inverse problem

1. Generate displacement data x(tᵢ) from known parameters, for three regimes:

| Dataset | Regime | Parameters (A, γ, ω) |
|---|---|---|
| `data1` | undamped | 1, 0, 1 |
| `data2` | underdamped | 3, 0.3, 1 |
| `data3` | overdamped | 3, 1.6, 0.5 |

2. Fit each dataset to the general solution with `FindFit` and recover (A, γ, ω).

## Results

`FindFit` recovered the true parameters in all three regimes:

| Dataset | Fitted A | Fitted γ | Fitted ω |
|---|---|---|---|
| `data1` | 1.0 | ≈ 0 (−1.8×10⁻¹⁵) | 1.0 |
| `data2` | 3.0 | 0.3 | 1.0 |
| `data3` | 3.0 | 1.6 | 0.5 |

**Limitation:** the data is synthetic and noise-free, so exact recovery is expected. This is a method demonstration, not a robustness study. [Optional: add a noisy-data result here if you run one.]

## Files

- `Inverse Analysis of Damped Oscillations.nb`: the Mathematica notebook (interactive; needs Mathematica or the free Wolfram Player)
- `Inverse Analysis of Damped Oscillations.pdf`: static export with all outputs, viewable without Mathematica

## Run it

Open the `.nb` file in Mathematica or Wolfram Player and evaluate all cells. The `Manipulate` sliders work interactively.
