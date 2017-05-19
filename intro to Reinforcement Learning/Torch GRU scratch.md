# Overview

A simple vanilla RNN implementation of a Shakespeare generator with pyTorch. The generator is trained character by character, using a single layer GRU unit. 

### Surprises

1. The LSTM and GRU units in pyTorch assumes full back-propagation through time (BPTT) length as the sequence that is fed in. AKA there is no need to loop in python to have the BPTT properly.

    A side effect of this is that the BPTT is the same as the sequence length, therefore long sequences are going to grow linearly in forward and backward compute time, which is nothing out of ordinary.
    
    **TLDR;**: If you were implementing vanilla RNN and was manually looping to get BPTT, don't worry here. torch GRU and LSTM already does that, and the time_steps is the same as the sequence length.
    
2. **It turned out the temperature in the self-feeding generator is crucial.**

    **What went wrong the first time**: 
    
    It turned out that the network itself was training okay. It was just that the generator was using an `argmax` for the next character selection, instead of doing a multinominal selection w.r.t. to the weights given by the softmax. 
    
    Effectively, `argmax` is equivalent to the Boltzmann distribution taken to the limit where $T\rightarrow 0$
    $$
    \mathrm{argmax}\bigg[\mathrm{softmax}@Y_{output} \bigg] \equiv \frac 1 Z \cdot e^{y_i/k_\beta T} 
    \bigg\vert_{T\rightarrow 0}.
    $$
    In this limit, the distribution is effectively frozen, and the state with the largest energy always gets picked. As it turned out, the character with the highest activation is not necessarily the best choice. Using a temperature ($k_\beta T$) gives much better result.
    
    Temperatures anywhere from 0.01 to 1 works well. The higher temperature gives a more garbled result, while the lower temerpature tend to quickly enter short repetive sentences.
    
    Now with the benefit of hind-sight, it is easy to understand why. The training is done using `softmax`
    $$
    \mathrm{softmax}:= e^{yi} \equiv \frac 1 Z \cdot e^{y_i/k_\beta T}\bigg\vert_{k_\beta T\rightarrow 1}.
    $$ 
    And as a result, the network is expected to hit whatever prediction accuracy when the output is a multinomial draw over this distribution. Althought the sampling mechanism can be different during the generative stage, large deviations from this limit will lead to very different results those during training.


### Todo:
all done

### Done:
- [x] Add temperature to generator
- [x] get training to work
- [x] use optim and Adam
- [x] add self-feeding generator