# Solving the 1D Wave Equation using FEM and Backward Euler

## Abstract

This paper describes a numerical approach to solving the one-dimensional wave equation using the Finite Element Method (FEM) for space and a coupled backward Euler scheme for time. The implementation models wave propagation in a fixed domain with Dirichlet boundary conditions.

---

## Problem Definition

We solve the wave equation:

\[
\frac{\partial^2 u}{\partial t^2} = c^2 \frac{\partial^2 u}{\partial x^2}, \quad x \in [0, 10], \ t \in [0, 2\pi]
\]

Initial conditions:
- Displacement: \( u(x, 0) = \sin\left(\frac{4\pi x}{10}\right) \)
- Velocity: \( \frac{\partial u}{\partial t}(x, 0) = 0 \)

Boundary conditions:
- Dirichlet: \( u(0, t) = u(10, t) = 0 \)

---

## Numerical Method

The PDE is reformulated into a system of first-order equations and discretized as:

\[
M u_{tt} + c^2 A u = b
\]

This is integrated in time using a coupled Backward Euler scheme:

\[
\begin{bmatrix} M & -\frac{k}{2}M \\ \frac{c^2 k}{2}A & M \end{bmatrix}
\begin{bmatrix} u^{n+1} \\ v^{n+1} \end{bmatrix}
=
\begin{bmatrix} M & \frac{k}{2}M \\ -\frac{c^2 k}{2}A & M \end{bmatrix}
\begin{bmatrix} u^n \\ v^n \end{bmatrix}
+
\begin{bmatrix} 0 \\ k b \end{bmatrix}
\]

The stiffness matrix \( A \), mass matrix \( M \), and load vector \( b \) are assembled using the standard FEM approach.

---

## Results

The solution demonstrates wave propagation that respects the initial profile and boundary conditions. The displacement profile \( u(x, T) \) reflects the dynamic behavior after one cycle of evolution.

---

## Conclusion

The finite element + backward Euler method provides a stable and effective framework for solving second-order hyperbolic PDEs. This framework can be extended to higher dimensions and variable coefficients.