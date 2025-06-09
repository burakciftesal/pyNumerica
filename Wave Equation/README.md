# Wave Equation Solver using FEM and Backward Euler

## Overview

This project solves the 1D wave equation:

\[
\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial x^2}
\]

using:
- **Finite Element Method (FEM)** for spatial discretization
- **Backward Euler Method** for time integration (in a coupled system form)

---

## Problem Setup

- Domain: \( x \in [0, 10] \)
- Time interval: \( t \in [0, 2\pi] \)
- Initial condition:
  - Displacement: \( u(x, 0) = \sin\left(\frac{4\pi x}{10}\right) \)
  - Velocity: \( \frac{\partial u}{\partial t}(x, 0) = 0 \)
- Boundary conditions: Dirichlet (zero) via penalty method

---

## Numerical Method

1. Discretize the domain using linear elements.
2. Assemble the **mass matrix** and **stiffness matrix**.
3. Use **Backward Euler** method in time with a coupled update system.

The semi-discrete system is:

\[
M u_{tt} + c^2 A u = b
\]

Converted to first order system and updated via:

\[
\begin{bmatrix} M & -\frac{k}{2}M \\ \frac{c^2 k}{2}A & M \end{bmatrix}
\begin{bmatrix} u^{n+1} \\ v^{n+1} \end{bmatrix}
=
\begin{bmatrix} M & \frac{k}{2}M \\ -\frac{c^2 k}{2}A & M \end{bmatrix}
\begin{bmatrix} u^n \\ v^n \end{bmatrix}
+
\begin{bmatrix} 0 \\ k b \end{bmatrix}
\]

---

## Usage

### Requirements
```bash
pip install numpy matplotlib
```

### Run the Solver
```bash
python wave_solver.py
```

This will display a plot of the wave displacement at the final time.

---

## Output

- Plot of displacement \( u(x, T) \)
- FEM-based solution of a wave propagating over a fixed domain