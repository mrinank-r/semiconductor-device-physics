# Homojunctions

Numerical simulations of 1D silicon p-n homojunctions under thermal equilibrium.

This section progressively develops a semiconductor junction solver, starting from the one-dimensional Poisson equation and building toward a self-consistent nonlinear solution for carrier distributions and electrostatic potential.

## Notebooks

### 01. Poisson equation solver

`01_constant_charge_poisson.ipynb`

A basic 1D Poisson equation solver with constant charge density.

The equation

$$\frac{d^2 V}{dx^2} = -\frac{\rho}{\epsilon}$$


is discretized using finite differences and solved as a linear system.

The numerical solution is compared with the analytical solution to verify the implementation.

### 02. Abrupt p-n junction

`abrupt_pn_junction.ipynb`

Extends the Poisson solver to an abrupt silicon p-n junction using the depletion approximation.

The model calculates:

- Doping and charge-density profiles
- Electrostatic potential
- Electric field
- Depletion-region widths

### 03 — Linearly Graded p-n Junction

`03_graded_pn_junction.ipynb`

Extends the model to a linearly graded p-n junction and solves the nonlinear Poisson equation self-consistently.

The model includes:

- Position-dependent doping
- Electron and hole concentrations
- Electric field and potential profiles
- Nonlinear Poisson equation
- Newton-Raphson iteration

The nonlinear system is solved by iteratively updating the potential until the maximum potential correction falls below a specified convergence tolerance.

## Assumptions

The current simulations assume:

- Silicon
- One-dimensional geometry
- Thermal equilibrium
- Nondegenerate semiconductor statistics
- Boltzmann carrier statistics
- Complete dopant ionization
- Constant permittivity
- No applied external bias

## Project Progression

The notebooks are intentionally ordered from simplest to most
physically complete:

$$ \text{Poisson} \rightarrow \text{abrupt junction} \rightarrow \text{graded junction} $$
