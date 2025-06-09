# Heat Equation Solver using FEM and Backward Euler

## Abstract

This paper presents a numerical approach to solving the 1D heat equation using Finite Element Method (FEM) for spatial discretization and Backward Euler for time integration. The method is demonstrated using Python, and results are validated by monitoring temperature evolution across the rod.

---

## Problem Description

We consider the heat equation:
\[
\frac{\partial u}{\partial t} = \frac{\partial}{\partial x} \left(a(x) \frac{\partial u}{\partial x}\right) + f(x)
\]
with the following setup:
- Domain: \( x \in [0, 1] \)
- Time: \( t \in [0, 10] \)
- Initial condition: \( u(x, 0) = 1 + x^2 \)
- Boundary conditions: \( u(0,t) = 1, \ u(1,t) = 2 \)
- Conductivity: \( a(x) = 1 \)
- Heat source: \( f(x) = 0 \)

---

## Numerical Method

- **Space Discretization:** FEM using linear elements
- **Time Discretization:** Backward Euler

The update formula is:
\[
(M + \Delta t A) u^{n+1} = M u^n + \Delta t b
\]

Matrices:
- \( M \): Mass matrix
- \( A \): Stiffness matrix
- \( b \): Load vector

---

## Results

The solver generates plots for:
- Initial temperature
- Evolution at time points \( t = 0.1, 0.2, 0.5, 1 \)

These demonstrate the diffusion of heat along the rod.

---

## Conclusion

The solver successfully models the heat distribution over time with boundary constraints using a robust and generalizable FEM framework. It can be extended to variable conductivities and non-zero heat sources.

---