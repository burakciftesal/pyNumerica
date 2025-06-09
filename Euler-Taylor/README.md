# Euler and Taylor Methods for Solving First-Order ODEs

## Overview
This project implements two classic numerical methods for solving ordinary differential equations (ODEs): the **Euler Method** and the **Second-Order Taylor Method**. The numerical results are compared with the exact analytical solution of the ODE. The implementation is done in Python using `NumPy` and `Matplotlib`, and is based on a MATLAB project converted into Python.
---

## Problem Statement

We aim to numerically solve the following first-order ODE:

$\frac{du}{dt} = (1 - \frac{4}{3}t)u$

with the exact solution:

$u(t) = 6 - 2e^{-t} - 3e^{-t/2}$

The initial condition is:

$u(0) = 1$

The solution is computed in the time interval $t \in [0, 5]$ using a step size of $h = 0.1$.

---

## Numerical Methods

### Euler Method

The Euler method uses the first-order Taylor expansion:

$u_{n+1} = u_n + h f(t_n, u_n)$

### Second-Order Taylor Method

This method uses the second-order Taylor expansion:

$u_{n+1} = u_n + h f(t_n, u_n) + \frac{h^2}{2} f'(t_n, u_n)$

Where $f'(t, u)$ is a custom-defined approximation of the derivative of $f(t, u)$.

---

## Python Implementation

The solver includes:

* Function definitions for $f(t, u)$ and $f'(t, u)$
* Step-by-step iteration using both Euler and Taylor methods
* Exact solution computation
* Error calculation
* Plots:

  * Exact vs Euler vs Taylor
  * Absolute error comparison
  * Logarithmic Euler error

---

## Requirements

```bash
pip install numpy matplotlib
```

---

## Usage

You can run the script `euler_taylor_solver.py`. The script will prompt for:

* Initial time: ()
* Initial value: ()
* Step size: ()

It will then produce comparative plots and error graphs.

---

## Output

* **Red line**: Exact analytical solution
* **Blue dashed line**: Euler approximation
* **Cyan dotted line**: Taylor approximation

You will also see a plot comparing the absolute errors of both methods, and a semilog plot of Euler's error.

---
## Summary

This project highlights how Euler and Taylor methods behave on a well-defined ODE. It visually and numerically demonstrates how the Taylor method, with its second-order accuracy, provides a significantly better approximation than Euler.
---