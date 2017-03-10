# Kullback-Leibler (KL) Divergence

$KL(P\;\Vert\;Q)$ is the information *gained* going from distribution $Q$ to $P.$ Or rather, the information *lost* in a model $Q$ from the true distribution $P$. 

> Also called:  
> **Information gain** in *machine learning*  
> **Relative entropy** of $P$ w.r.t. $Q$ in *information theory*

For discrete probability distributions $P$ and $Q$, the KL divergence is defined as 
\begin{align}
KL(P\;\Vert\;Q) = \sum_i{P_i \log{\frac{P_i}{Q_i}}}.
\end{align}
This can be re-written as the expectation value of the entropy of the conditional probability distribution $Q_i/P_i$
\begin{align}
KL(P\;\Vert\;Q) = \bigg\langle - \ln \frac q p \bigg\rangle.
\end{align}

### Gibbs Inequality

As a result, we can prove Gibbs' inequality
\begin{align}
KL(P\;\Vert\;Q) &= - E\bigg[\ln \frac q p \bigg]\\\
& \ge - \ln{E \bigg[ \frac q p \bigg]} \\\
& = - \ln \sum{P_i \frac{Q_i}{P_i}} \\\
& = 0.
\end{align}
The inequality follows from the convexity of $-\ln$. 

## Bayesian Updating

In Bayesian statistics, we can use the KL divergence to measure the *information gain* in moving from a prior distribution $p(x)$ to a posterior distribution $p(x|I)$. Using Bayes' theorem,
$$p(x|y, I) = \frac{p(y|x,I)p(x|I)}{p(y|I)}$$

### Properties
- asymmetric
- is convex
- 