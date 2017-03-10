# Restricted Boltzmann Machines, Physics, and StatMech

## Writing Plan

- What is Boltzmann Machine? (RBM, LR)
- derivation of Boltzmann distribution and MLE
- difference between Boson statistics and Boltzman statistics 




## What is Botzmann Machine


## Boltzmann Distribution, Why, and What Exactly Is Happening?

In physics, when describing a collection of particles in thermal equilibrium, we frequently encounter a statistical model called the Boltzmann Distribution. 
\begin{align}p_i = \frac{e^{-\epsilon_i/kT}}{\sum_{j=1}^M{e^{-\epsilon_j/kT}}}.\end{align} 
This distribution is derived from the Canonical Emsemble \begin{align}P = e^{\frac{F-E}{k_\beta T}}.\end{align} 

The Canonical Ensemble[^1] is a simple statistical mechanics model where a single particle is in thermal equilibrium with a large heat bath. Let's suppose that we have one particle in a box in thermal contact with a large reservoir. Intuitively, we would assume that if the "temperature" of the particle and the heat bath surrounding it is the same, the system would be in equilibrium. So what does "in equilibrium" mean? 

At equilibrium, the energy influx and outflow would be the same on average
$$dU_{in} = dU_{out}.$$

When we talk about temperature of a simple system like this, we assume that the total energy of a system is only a function of its temperature. In the case of idea gas, we assume that there is no volume change or chemical processes
$$\mathrm{def}\; U(T).$$
If we can assume this simple functional form for the total energy $U$ at temperature $T$, then we can analize the 

There is thermodynamics and then there is stat-mech. You can think of these two being the classical and historical approach working with idea gas, versus a more quantum approach that assumes quantization of the state space and indistinguishability of the particles involved from the very begining. 

### How is the Boltzmann distribution derived?

The Cannonical Ensemble is an ideal model concerning a single microstate and a heat bath. Let's suppose that we have one particle in a box in thermal contact with a large reservoir. Intuitively, we would assume that if the "temperature" of the particle and the heat bath surrounding it is the same, the system would be in equilibrium. At equilibrium, the energy influx and outflow would be the same on average. This would be the first axiom.



> For an ensemble of particles, the probability that this system will be in state $i$ is 
> $\begin{align}p_i = \frac{e^{-\epsilon_i/kT}}{\sum_{j
> =1}^M{e^{-\epsilon_j/kT}}}.\end{align}$
> 
> What does it mean for "the system [to be] in state $i$"? 
> 
> Well, it means the 

Now let's try to derive 
\begin{align}E=\sum_{i=0}^\infty n_i \epsilon_i\end{align}
where $n$ is the number of particles, and this 
[^2]

## Softmax

The softmax takes an energy and gives a score. A score of a set of colors at that pixel. for Adjacent pixels, calculate a cost for the adjacent pixel to be different. We get a graphical model. A score for every color / pixel, and a score for smoothness. For each colorization we can get an energy for the colorization. 

The fundamental problem is modeling exponential distributions. Softmax is over an "exponential space". Feedforward computation via a deep network, an exponential softmax (which we can not really do). get a log(loss) of the probability of the actual colorization.
$$l = -\ln P(y)$$
a


## References 

[^0]: http://micro.stanford.edu/~caiwei/me334/Chap8_Canonical_Ensemble_v04.pdf
[^1]: https://en.wikipedia.org/wiki/Boltzmann_distribution
[^2]: https://en.wikipedia.org/wiki/Canonical_ensemble
[^3]: Maximum Likelihood Estimation derivation of the boltzman distribution http://bouman.chem.georgetown.edu/S98/boltzmann/boltzmann.htm
[^4]: another MLE derivation
http://bcs.whfreeman.com/webpub/Ektron/Tipler%20Modern%20Physics%206e/Classical%20Concept%20Review/Chapter_8_CCR_7_Derivation_of_the_Boltzmann_Distribution.pdf