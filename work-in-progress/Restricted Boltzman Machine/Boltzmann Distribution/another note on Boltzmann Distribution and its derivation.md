## Forwords and References

In writing of this note, I found Cai Wei's notes for his course ME334 at 
Stanford the most helpful. His class notes for course ME334 is advanced yet 
short and succinct, allowing me to draw high-level connections with the 
concepts fitting perfectly in my work memory.

I highly recommend you take a quick look here: 
[ME346A Lecture Notes](http://micro.stanford.edu/~caiwei/me334).

## How is Boltzmann Distribution Derived?

Boltzmann distribution 
\begin{align}P_\epsilon = 
\frac
{e^{\epsilon/k_\beta T}}
{Z}\end{align} 
describes the probablity distribution across enenergies
for a small collection of fixed number of particles in thermal equilibrium with
a heat bath. This ensemble is called the [Canonical Ensemble](//www.wikipedia.org/wiki/Canonical_Ensemble). In the Canonical 
Ensemble, the volume $V$, temperature $T$, and particle number $N$ are
all conserved.

$Z$ in the expression above is the [partition function](//en.wikipedia.org/wiki/Partition_function). 
\begin{align}Z=\sum_{i}{e^{\epsilon_i/k_\beta T}}.\end{align}
This partition is derived from the more fundamental [Microcanonical Ensemble](
//en.wikipedia.org/wiki/Microcanonical_ensemble), where instead of the 
temperature $T$, the overall energy $E$ of the ensemble is conserved. 
You can think of the microcanonical ensemble being a small box of particles in 
thermal isolation. There is no heat going in and out. We can not derive the 
definition of temperature from the microcanonical ensemble, but we can develop 
the concept of entropy.

In this perfectly isolated system, the multiplicity of phase states for the
small number of particles is conserved. If we call this multiplicity of
$\Omega$, then any partition of this ensemble (the box and its content)
should have a multiplicity 
\begin{align}\Omega_{total} = \Omega_{\text{part a}} \Omega_{\text{part b}}.\end{align}
Now with the idea that in the microcanonical ensemble the energy, volume and 
particle number $(E, V, N)$ completely defines the statistical state of the 
system, and the entropy has to be a pure function of the other three quantities
\begin{align}S(E, V, N),\end{align}
we can can use the assumption of "extensivity" to argue that the entropy has to
take the logorithmic form
\begin{align}S = k \log{\Omega}\end{align}
where $k$ is a constant. 

Extensivity means that when we double either $E$, $V$ or $N$, the total entropy
has to increase linearly, making the entropy an intensive parameter of the 
state. This way, the entropy of the system can be a simple 
sum of the entropy its constitutes.

Happy with this clean definition of entropy, we now want to figure out what 
temperature is. The microcanonical ensemble does not define temperature because 
it is an isoenergetic model (constant $E$). It could undergo 
irreversible changes in it's volume that leads to a change in the total entropy. 
To develop the concept of temperature we need to work with the canonical 
ensemble, where a small ensemble is kept in thermal equilibrium with a large
thermostat (thermal bath). This equilibrium allows as to set a well defined 
temperature for the system. In this new model, the state is completely defined
by $N$, $V$, and temperature $T$. Temperature replaces total energy $E$ in the 
state equation
\begin{align}S(N, V, T).\end{align}

Now to develop the concept of temperature, we need to use extensivity. The 
canonical ensemble is extensible. What it means is that if you double either one
of the quantities the total entropy also double. 

Let's recap. 

Conservation of this "multiplicity" is a key assumption. In a reversable 
process, the total entropy of the isolated system remains constant. 


The logarithmic 
form conforms naturally with the exponential form of your familiar Boltzmann 
distribution and other entropy definitions from information theory.
