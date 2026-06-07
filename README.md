
# PINN for Lotka-Volterra Predator-Prey System

## What this project does
Solves the classic Lotka-Volterra predator-prey ODE system in two ways:
1. Classical numerical solver (scipy odeint)
2. Physics-Informed Neural Network (PINN) built in PyTorch

Compares both solutions visually to show where and why PINNs are useful.

## The ODE System
dx/dt = αx - βxy   (rabbits)
dy/dt = δxy - γy   (foxes)

Where x = prey (rabbits), y = predators (foxes), t = time.

## Why PINNs?
Classical solvers step forward in time numerically.
PINNs train a neural network whose loss function penalises
any violation of the governing ODEs — the biology is baked into training itself.

## How to Run
pip install numpy scipy matplotlib torch jupyter

Run classical_solver.ipynb first, then pinn_solver.ipynb, then compare.ipynb

## Results
(comparison plot coming soon)
