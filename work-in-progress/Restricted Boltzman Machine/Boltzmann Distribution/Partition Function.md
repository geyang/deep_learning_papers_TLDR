# Boltzmann Distribution, Partition Functions and Entropy

$$
\newcommand\diff{\mathop{}\!\mathrm{d}\,}
\newcommand\def{\mathrm{def}\;}
$$

The softmax function and the restricted Boltzmann machines are commonly referred
to by people in the ML field as physically inspired. As a physicist, I want to 
study the inspiration of these concepts within physcs, and disentangle those
inspired by termodynamic analysis of the idea gas versus those intuitions that
arises purely from statistical considerations.

As it turned out, if you take a quantum and statistical approach, all of these 
are in fact inspired by statistics. So in the end, what statistical machine
learning is attributing to physics is simply what physicists borrowed from 
the field of statistics. Understanding how these physical concepts are built-up
helps provide a better intuition of these statistical and informational 
theoretic quantities as well.

Let's dive in.

## Boltzmann Distribution, Softmax, and Partition Function

The partition function used in Boltzmann Distribution
\begin{align}
Z = \sum{e^{-\beta \epsilon}}
\end{align}

What they are. What do they need.

## What is Temperature, Entropy, and Energy?

### Entropy
The log of multiplicity of a state. Using product rule of multiplicity we derive
the logorithmic formula for entropy. This is fundamental. 

The Boltzmann factor has a unit and approaches zero in the thermodynamic limit.
We can compare the statistical definition of entropy we just developed vs one
from state functions in classical thermodynamic, the thermodynamic definition
only tells us the differential relationship between the energy and the 
temperature

Another benefit is that with this statistical definition, S automatically 
becomes extensive, which is something we have to assume in thermodunamics to
derive the concept of temperature.

### Energy and Temperature

Suppose we work with a small two-level quantum system. The energy of the two
states are simply lables that allows us to distinguish them from each other.
The multiplicity of the two states, both being 1, means the entropy of this
small system is zero when it is in either state (let's ignore quantum 
superposition atm). Energy also helps in providing a conservation rule. 

To take advantage of energy conservation, we need to first develop the idea
of temperature. Classically, temperature is derived by assuming extensivity
with the entropy state function. Soon you will see that in the quantum approach,
termperature can be derived purely from thermal equilibrium based on energy 
conservation and maximum multiplicity. Maximum multiplicity is the same as the
second law of thermal dynamics.

Take two systems $\Sigma_1$ and $\Sigma_2$. Suppose the multiplicity of the two 
systems are $\Omega_1$ and $\Omega_2$ and they are in thermal equilibrium. If we
assume that in thermal equilibrium, the entropy is maximized for this collective
system, then at any time a small perturbation of the multiplicity of these 
sub-systems should lead zero change in the overall multiplicity
\begin{align}
\diff{\Omega_{total}}=\diff\Omega_1\Omega_2 +
\Omega_1\diff{\Omega_2}=0
\label{multiplicity_equation}
\end{align}

Given that the for these two systems, energy uniquely identifies the state, the 
entropy has to be a pure function of the total energy
$$\def{S(U)}.$$
Now remember 
$$S=k_\beta\ln{\Omega},$$
then we have
\begin{align}
\diff{\ln\Omega}=\frac{\partial\ln\Omega}{\partial U}\cdot\diff U.
\end{align}

Take equation $\eqref{multiplicity_equation}$.