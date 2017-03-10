# Simple Canonical Ensemble

the degree of freedom is ${n_i}$, $i = 1, ..., N.$

The energy of the molecule $i$ is $(n_i\cdot \epsilon), n_i = 0, 1, 2.$

We use canonical ensemble. The first step is to figure out the partition 
function
\begin{align}Z=\sum_{\{n_i\}}{\exp{(-\beta H)}}\end{align}
where \begin{align}H=\sum_{i=1}^{N}{n_i\cdot\epsilon},\end{align}
is the ensemble average Helmholtz free energy. and the sum above is over all 
possible combinations of $\{n_i\}$. This seems daunting to perform, but it can 
be simplified
\begin{align}e^{-\beta H} 
& = \exp{(-\beta \epsilon \sum_{i=1}^{N}{n_i})} \\
& = \prod_{i=1}^{N}{e^{-\beta\epsilon n_i}}
.\end{align}
so
\begin{align}Z
& = \sum_{\{n_i\}}{\prod_{i=1}^{N}{e^{-\beta\epsilon n_i}}} \\
& =  .\end{align}
