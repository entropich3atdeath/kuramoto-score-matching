In this notebook, we learn a time-varying coupling matrix for a system of Kuramoto oscillators to trace out a given trajectory as it evolves under Langevin dynamics.

We use Vincent's formula to calculate the score - 1st with Gaussian noise and then given we are using phase angles on S^1, we calculate the score using von Mises noise.

Finally, we notice that the gradients calculated using von Mises noise itself has the same form as the dynamics of a Kuramoto oscillator equation. So in the last part of the notebook, we replace autograd gradient calculation with a set of meta-oscillators. As these meta-oscillators evolve forward in time according to the Langevin equation, they will calculate the gradients needed by the coupling matrix of the oscillators learning the trajectory.
Thus, by controlling the speed of the Langevin steps, we have 2 layers of oscillators simply moving forward in time but calculating the necessary gradients needed.
