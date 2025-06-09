# Heat Equation Solver using FEM and Backward Euler Method

## Overview

This project implements a numerical solver for the one-dimensional heat equation using:
- **Finite Element Method (FEM)** for spatial discretization
- **Backward Euler Method** for time integration

It models the temperature distribution along a rod over time, subject to fixed boundary conditions and an optional heat source.

---

## Mathematical Model

We solve the heat equation:
\[
\frac{\partial u}{\partial t} = \frac{\partial}{\partial x} \left(a(x) \frac{\partial u}{\partial x}\right) + f(x)
\]

With:
- \( a(x) = 1 \): constant conductivity
- \( f(x) = 0 \): no internal heat source
- Boundary conditions: \( u(0,t) = 1, \ u(1,t) = 2 \)
- Initial condition: \( u(x, 0) = 1 + x^2 \)

---

## Numerical Method

1. The domain \([0, 1]\) is discretized into finite elements.
2. The **mass matrix** \(M\), **stiffness matrix** \(A\), and **load vector** \(b\) are assembled.
3. The time stepping uses the **Backward Euler method**:
\[
(M + \Delta t A) u^{n+1} = M u^n + \Delta t b
\]

---

## Usage

### Requirements
```bash
pip install numpy matplotlib
```

### Run the code
```bash
python heat_solver.py
```

You will see plots showing the evolution of temperature at different time steps.

---

## Output

- Initial condition
- Temperature profiles at \( t = 0.1, 0.2, 0.5, 1.0 \)
- Final temperature at \( t = 10 \)

---

## File Structure

```
heat_solver.py
heat_README.md
heat_paper.md
```

---

## License

MIT License