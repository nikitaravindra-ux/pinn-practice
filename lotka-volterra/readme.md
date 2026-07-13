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
- [x] Day 5: Comparison plot + final cleanup

## How to Run
pip install numpy scipy matplotlib torch jupyter

Then open classical_solver.ipynb in Jupyter notebook.

## Results
![Comparison Plot](comparison_plot.png)

## notes

- A pure PINN (physics loss only) kept collapsing to zero — because x=0, y=0 
  trivially satisfies the ODE mathematically. The network found the easy way out.

- Fixed by adding a data loss term alongside the physics loss, forcing the network 
  to match the classical solution at sampled points.

- This is realistic — real-world PINNs almost always combine physics loss 
  with some measurement data. That combination is their true strength.

- The Lotka-Volterra system is deceptively hard for PINNs due to its long 
  oscillatory nature — a known challenge called spectral bias.
