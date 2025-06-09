# Finite Element Method (FEM) for Boundary Value Problems

## 🔍 Overview
This project implements the Finite Element Method (FEM) in Python to solve a one-dimensional boundary value problem (BVP) of the form:

\[
- u''(x) = f(x), \quad x \in (0,1), \quad u(0) = 0, \quad u(1) = 0
\]

The method uses a non-uniform mesh and linear basis functions. Both the numerical FEM solution and the exact analytical solution are plotted and compared.

---

## 🧮 Problem Statement

- **Differential equation:**
  \[
  -u''(x) = 1
  \]

- **Boundary conditions:**
  \[
  u(0) = 0, \quad u(1) = 0
  \]

- **Exact solution:**
  \[
  u(x) = -\frac{x^2}{2} + \frac{x}{2}
  \]

---

## ⚙️ Methodology

- **Mesh:**
  ```python
  x = [0, 1/6, 1/2, 1]
