## Entropy

Entropy $H(Y)$ is the measure of uncertainty of variable Y. For example for a bernouli distribution $P(i) = 1/N$. Then the entropy of this distribution is $$H(B) = \sum { P_i \ln \frac 1 P_i},$$ the expected value of logrithm of the multiplicity of each one of the tosses. 

When the multiplicity is large, the entropy is smaller

## KL Divergence

In Bayesian statistics, a model from prior distribution $P(x)$ to a posterial distribution $P(x|I)$ can be further updated by a new data $y$. The information gained in this process would then be the KL divergence between the two distributions 
$$
KL\bigg(P(\cdot |y, I) \; \Vert\; P(\cdot|I)\bigg) 
= \sum_x{P(x|y, I) \log \frac{P(x|y,I)}{P(x|I)}}
$$
and the information gained would be
\begin{align}
-\bigg[H@P_{(\cdot|y, I)} - H@P_{(\cdot| I)}\bigg]
    &= \sum{P_{(x|y,I)} (\log P_{x|y,I} - \log P_{x|I}})\\\
    &=
\end{align}

### Bayesian experimental design

Bayes d-optimal

maximising the expected Kullback-Leibler divergence between the prior and the posterior. 

### Cross-Entropy

$$H(p,m)=H(p)+D_{\mathrm {KL} }(p\|m),$$

### Differential Entropy 