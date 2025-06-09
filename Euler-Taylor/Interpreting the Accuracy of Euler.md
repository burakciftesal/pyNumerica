# Interpreting the Accuracy of Euler, Taylor, and Trapezoidal Methods for Solving First-Order ODEs

## Abstract

This paper presents a comparative study between the Euler, second-order Taylor, and Trapezoidal Euler numerical methods for solving first-order ordinary differential equations (ODEs). The target ODE has a known analytical solution, allowing for quantitative error analysis. Results demonstrate the improved accuracy of higher-order and semi-implicit methods, validating the theoretical expectations regarding their convergence behavior.

## 1. Introduction

Numerical methods provide essential tools for solving differential equations when analytical solutions are unavailable or impractical. Euler's method, as one of the simplest approaches, offers a baseline for approximation but suffers from significant error growth. Higher-order methods such as the second-order Taylor expansion and semi-implicit methods like the Trapezoidal Euler method improve accuracy and stability.

In this study, we solve the ODE:

$\frac{du}{dt} = (1 - \frac{4}{3}t)u$

with the exact solution:

$u(t) = 6 - 2e^{-t} - 3e^{-t/2}$

and initial condition $u(0) = 1$, using three different numerical techniques.

## 2. Methodology

### 2.1 Euler Method

Euler’s method approximates the next value based on the slope at the current point:

$u_{n+1} = u_n + h f(t_n, u_n)$

### 2.2 Taylor Method (Second Order)

This method extends the Euler method by incorporating the first derivative of the slope:

$u_{n+1} = u_n + h f(t_n, u_n) + \frac{h^2}{2} f'(t_n, u_n)$

where $f'(t, u)$ is estimated based on prior knowledge or symbolic differentiation.

### 2.3 Trapezoidal Euler Method

This semi-implicit method uses a predictor-corrector scheme. First, it predicts the next value using Euler's method, then corrects it using the average of slopes:

**Predictor:**
$u^* = u_n + h f(t_n, u_n)$

**Corrector:**
$u_{n+1} = u_n + \frac{h}{2} \left[f(t_n, u_n) + f(t_{n+1}, u^*)\right]$

This method provides better accuracy than standard Euler, especially at smaller step sizes.

## 3. Results

Visual comparisons between the exact solution and all three numerical methods show:

* Euler’s method diverges faster as $t$ increases.
* Taylor’s method closely tracks the exact solution throughout.
* Trapezoidal Euler provides accuracy improvements over Euler, though not as precise as Taylor.

Error analysis confirms:

* Euler: first-order accuracy
* Trapezoidal: better than first-order
* Taylor: second-order accuracy

Decreasing the step size from $h = 0.01$ to $h = 0.001$ significantly reduces error for the Trapezoidal method, confirming expected convergence behavior.

## 4. Conclusion

This project reinforces the theoretical understanding of numerical ODE solvers. While Euler's method is easiest to implement, both Taylor and Trapezoidal methods provide greater accuracy. The Taylor method achieves this through second-order precision, while the Trapezoidal method offers a practical compromise between simplicity and improved accuracy.