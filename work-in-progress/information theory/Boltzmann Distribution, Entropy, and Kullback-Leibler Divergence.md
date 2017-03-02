---
title: Boltzmann Distribution, Entropy, and Kullback-Leibler Divergence
mathJax: true
snippet: /projects/escherpad/escherpad-home-page-screen-shot.png
snippetHeight: 200px
snippetPosition: top
excerpt: <p>How to go from Statistical Mechanics to </p>
postLayout: "layout-6-column offset-2-column"
---
# Boltzmann Distribution, Entropy, and Kullback-Leibler Divergence

### A Physicist's Derivation of Entropy
From multiplicity assumption we have the definition of entropy
\begin{align}
S = k_\beta \ln{\Omega}.
\end{align}

Now, *temperature* in the system can be derived from the thermal 
equilibrium assumption in a Cannonical Ensemble (this is what it
means for two systems to be in thermal "equal terms").
\begin{align}
\frac{1}{T} = \frac{\Delta{S}}{\Delta{E}}.
\end{align}

For two microstates $1$ and $2$, the relative probability is
\begin{align}
\frac{P_1}{P_2} = e^{-\Delta{E}/k_\beta T}. \label{rel_P}
\end{align}
The minus sign comes from the assumption that the entropy of the 
two microstates are both 1 in the case of a two level system, and
it is the overall combined system for which the multiplicity 
needs to be conserved. (Canonical Ensemble)

Now we need to derive Shannon's entropy 
\begin{align}
H = -\sum_{i}{P_i \cdot \log{P_i}}. \label{def_H}
\end{align} Note the missing Boltzmann Constant
in this defintion. The thermodynamic defintion is different by
a factor $k_\beta$.

> **Note**: 
In thermodynamics, Boltsmann's constant is an important factor not 
only in grounding the entropy in real units, but also making sure
that terms are at the correct scale. $k_\beta$ is roughly $1/N_A$ 
where $N_A$ is the Avogadro's number. Thus in the thermodynamic 
limit where the partition function has a factor of $N \;\mathrm{mole}$
in the front, $k_\beta$ keeps the terms close to 1.

To derive $\eqref{def_H}$, we need the partition function. From 
$\eqref{rel_P}$ we can derive that 
\begin{align}
P_i = Z^{-1} \cdot e^{- \beta \epsilon_i} \label{def_P}
\end{align}
and the partition function for the total probability 
\begin{align}
Z = \sum_i{e^{-\beta\epsilon_i}}.
\end{align}

Note that in physics, the partition function $Z$ is an important 
quantity from which **every** important thermal dynamic variable 
can be derived. For example the energy of the system (expected
value of) is
\begin{align}
\langle E \rangle
& = Z^{-1}\sum_i{\epsilon_i \cdot e^{- \beta \epsilon_i}} \\\
& = - \frac{\partial{ \ln{Z}}}{\partial \beta}.
\end{align}
Similarly, we know that
\begin{align}
A = - k_\beta T \ln Z
\end{align} where $A$ is the [Helmholtz Free Energy]. It is usually 
derived via [Legengre Transformation] from entropy. Now remeber
\begin{align}
A = U - TS,
\end{align} therefore
\begin{align}
T S = U - A
\end{align}
\begin{align}
S =k_\beta \ln{Z} - T^{-1} \frac{\partial{\ln{Z}}}{\partial{\beta}}
\end{align} now take out a factor of $k_\beta$, and use $\eqref{def_P}$, 
we get Shannon's information entropy (eq. 5.31, page 89, Sturge)
\begin{align}
S & = - k_\beta \ln {\big[Z^{-1} \cdot e^{-\beta E}\big]}\\\
& = - k_\beta \sum{
P_i \ln{P_i}
}.
\end{align}

> **Note**:
$A$, $S$, $G$ (Gibbs free energy), and $H$ (enthalpy) are four main 
thermodynamic entities that are related by [Legengre Transformation]. 
There are 12 entities related this way but these four are the most 
commonly used in thermodynamics.


[Helmholtz Free Energy]: //wikipedia.org/wiki/Helmholtz_free_energy
[Legengre Transformation]: //wikipedia.org/wiki/Lagrange_Transformation

#### Interpretation

Equation $\eqref{def_H}$ can be rewritten as the expected value of 
$\ln{P_i^{-1}}$
\begin{align}
H & = \langle \ln{ P^{-1} }\rangle \\\
  & = \sum{P_i \ln{\frac{1}{P_i}}}.
\end{align}
It makes sense that in a distribution, $\ln{(1/P_i)}$ is the amount 
of information that such event $i$ carries. Consequently, the expected
value of $\ln(1/P_i)$ over all possible events $\{i\}$ is the information
entropy of the distribution. This information is the logrithm of the 
multiplicity of the system (the state space). Therefore entropy describes
the amount of disorder a distribution contains. 

> $H(x) \ge 0$, entropy is always non-negative. $H_x = 0$ when $X$ is deterministic.

#### Joint Entropy

Between two distributions $X$ and $Y$
\begin{align}
H(X,\;Y) &= - E_{x,\;y}\langle\ln P(X,Y)\rangle \\\
&=\sum_{x,\,y} p(x,\,y) \frac{1}{p_{x,\,y}}
\end{align}

#### Conditional Entropy 

The [conditional entropy] of two distributions $X$ and $Y$ is
\begin{align}
H(X\,|\,Y) = \sum_{x,\;y}{P(x_i, y_i) \ln{\frac{P(y_i)}{P(x_i, y_i)}}}.
\end{align}
To derive, use Bayes' Law. 

> **Notice** that $$
H(X|Y)\neq H(Y|X)
$$.

[conditional entropy]: //en.wikipedia.org/wiki/Conditional_entropy 

It is also easy to develop the *chain rule*
$$H(X, Y ) = H(X) + H(Y |X)$$ 
and a corollary
$$H(X, Y |Z) = H(X|Z) + H(Y |X, Z)$$

Now let's summarize what we have so far.

- Entropy $H(X)$ is the log of state space (uncertainty) or "self-information" of a single random variable (probability distribution). 
- Conditional entropy $$
H(X|\,Y)
$$ is the entropy of one random variable conditioned upon the knowledge of another.

- The reduction in uncertainty from $H(X)$ to $H(X|\,Y)$ is the *mutual information*
\begin{align}
I(X;\,Y) := H(X) - H(X|\,Y).
\end{align}

- incidentally, the *channel capacity* $C$ of a communication channel is defined as $$C = \max_{p(X)} I(X;\,Y)$$

#### Relative Entropy (Kullback-Leibler Divergence)

The KL divergence is now looking very similar to the conditional
entropy defined above sans a negative sign. Typically, $P$ represents the "true" 
distribution (data) and the $Q$ represents a model or a theory.
\begin{align}
KL(P\,\Vert\,Q) &= \bigg\langle\ln{\frac{P_{(x)}}{Q_{(x)}}} \bigg\rangle\\\
&=\sum{P_i \ln{\frac{P_i}{Q_i}}}.
\end{align}
This is consistent with the meaning that $KL$ divergence is the
difference between distibution $P$ on $Q$. Notice that

- $KL(P\,\Vert\,Q)$ is asymmetric (hence not a true metric)
- semi-definite: $\forall P, Q,\; KL(P\,\Vert\,Q) \ge 0.$
- linearlly additive for *independent* $P_i$'s and $Q_i$'s.

The semi-definitiness can be proven via Gibbs inequality.

#### Mutual Information (Interms of divergence)

The mutual information can be expressed in terms of the KL divergence
\begin{align}
I(X;\,Y) := KL(p(x,y)\,\Vert\,p(x)\,p(y))
\end{align}
This is the information gained when moving from a model that assumes independence between $x$ and $y$ to their joint distribution. 

#### Von Neumann Entropy in Quantum Systems

To adapte this classical definition of entropy to quantum mechanics,
we can just use density matrix and the trace instead (via Von Neumann)
\begin{align}
H = - k_\beta \mathrm{Tr} (\rho \ln \rho).
\end{align}



[^1]: http://www.ece.tufts.edu/~maivu/ES250/1-entropy.pdf