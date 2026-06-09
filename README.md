# PINN for Lotka-Volterra Predator-Prey System

## What this project is
Solving the classic Lotka-Volterra predator-prey ODE system in two ways:
1. Classical numerical solver (scipy odeint)
2. Physics-Informed Neural Network (PINN) built in PyTorch

Then comparing both solutions visually.

## Why PINNs?
Classical solvers like scipy step forward in time numerically.
PINNs instead train a neural network whose loss function penalises
any violation of the governing ODEs — the biology is baked into the training.

## The ODE System
dx/dt = αx - βxy   (rabbits)
dy/dt = δxy - γy   (foxes)

Where x = prey (rabbits), y = predators (foxes), t = time.

## Progress
- [x] Day 2: Classical scipy solver
- [x] Day 3: Understanding PINN theory
- [x] Day 4: PINN implementation in PyTorch
- [ ] Day 5: Comparison plot + final cleanup

## How to Run
pip install numpy scipy matplotlib torch jupyter

Then open classical_solver.ipynb in Jupyter notebook.

## Results
(comparison plot will be added on Day 5)
