# Swarm-particle-optimization
### The target is to develop an application finding the minimum of a function in a given interval using swarm  particle optimization. The function is given as a parameter in the code, and should have type  std::function<float(float, float)>. The Swarm Particle Optimization (SPO) uses particles to explore the state  of solutions. It is an iterative process where a set of particles, initially spread randomly across the solution  space, autonomously travel the solution space driven by local and global knowledge relative to the  solution explored so far. 
## The SPO pseudocode can be summarized as follows:
## INITIALIZATION: 
### a. distribute n particles across the search space (uniform distribution)
### b. evaluate the objective function f for each particle position and assign the computed value as local optimum
### c. assign to the global optimum the “best” computed local optimum 
### d. randomly initialize particle velocities
## ITERATION: 
### a. for each particle, update position as a function of current velocity, distance from local  optimum and distance from global optimum. 
### b. re-evaluate local and global optima
## The key point in the algorithm is the iteration step. Usually: 
### a. Velocity is updated as a linear combination of current velocity, distance from local optimum and  distance from global optimum. Multiplicative coefficients in the linear combination are execution  parameters (same for all particles). Distance from local/global optima are weighted with a random  number Ri in [0,1] V(t+1) = a V(t) + b R1 (Pos(t) - Pos(localOpt)) + c R2 (Pos(t) – Pos(globalOpt))
### b. Position is re-computed as the current position plus current velocity (i.e. assuming a single time  unit across iterations) Pos(t+1) = Pos(t) + V(t+1)
### The application computing the minimum of a function though SWO must provide as a result the global  minimum computed after niter iterations.
