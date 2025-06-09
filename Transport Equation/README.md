# Numerical and Analytical Solution of the 1D Linear Transport Equation

## Abstract
This study compares finite difference schemes and the analytical method of characteristics for solving the one-dimensional transport equation. Numerical stability, accuracy, and wave propagation behavior are visualized and compared.

---

## Equation

We aim to solve the following **1D linear transport equation**:

\[
\frac{\partial u}{\partial t} + c \frac{\partial u}{\partial x} = 0
\]

- This describes a wave or signal moving at **constant speed** \( c \).
- In our case:
  - **Wave speed**: \( c = 0.25 \)
  - **Initial condition**:
    \[
    u(x, 0) = 3 \cdot e^{-(x + 1)^2}
    \]
    A smooth bell-shaped curve centered at \( x = -1 \).

---

## Methods

### 1️⃣ Finite Difference Methods (Numerical)

We divide space and time into steps:
- \( \Delta x = 0.05 \)
- \( \Delta t = 0.1 \)
- Define \( r = \frac{c \cdot \Delta t}{\Delta x} \)

We then compute values over time using these update formulas.

#### 🔹 Forward Difference (FWD)

Approximates wave propagation:

\[
u_i^{n+1} = (1 + r) \cdot u_i^n - r \cdot u_{i+1}^n
\]

- Uses the current point and the next point.
- Can become **unstable** if \( r > 1 \).

#### 🔹 Upwind Difference (UWD)

Uses information from the "upwind" direction:

\[
u_i^{n+1} = (1 - r) \cdot u_i^n + r \cdot u_{i-1}^n
\]

- More **numerically stable**
- Suitable when wave moves rightward

---

### 2️⃣ Analytical Solution (Exact)

The **method of characteristics** provides an exact formula:

\[
u(x, t) = f(x - ct)
\]

- It shifts the initial condition by \( ct \)
- The shape of the wave **does not change**

With:
\[
f(x) = 3 \cdot e^{-(x + 1)^2}
\]
we get:
\[
u(x, t) = 3 \cdot e^{-(x - ct + 1)^2}
\]

---

## Implementation

- Time steps: 30
- Domain: \( x \in [-6, 8] \), \( t \in [0, 8] \)
- Plots: numerical approximations and exact surface
- Also plots characteristic lines: \( x = x_0 + ct \)

---

## Results

- FWD/UWD simulate the wave, with:
  - FWD: may oscillate or become unstable
  - UWD: more robust
- Exact solution confirms expected wave shift
- Characteristic lines illustrate solution path

---

## Conclusion

We compared finite difference and exact approaches to solving a basic wave transport problem. FWD and UWD have their trade-offs in stability, but both approximate the shifting wave shape. Characteristics give an exact view of how waves move without deformation.