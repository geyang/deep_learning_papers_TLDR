# Understanding deep learning requires rethinking generalization
Google Brain, 2017 ICLR Best Paper 

| Authors       | Chiyuan Zhang, Samy Bengio, Moritz Hardt, Benjamin Recht, Oriol Vinyals    | 
| ------------  |:------------ | 
| openreview | https://openreview.net/forum?id=Sy8gdB9xx&noteId=Sy8gdB9xx |
| paper link | https://openreview.net/pdf?id=Sy8gdB9xx |

## TLDR;

Through experimentation, authors shows how traditional approaches to generalization
failes to explain why large neural networks generalize well in practice. They also
explains why deep learning requires rethinking generalization.

## Surprises

During non-parametric randomization tests, authors rationalized random labels
destroyes learnable knowledge, therefore the network would fail to converge
or slow down substantially. Surprisingly, network converges just as fast. 
small generalization error might not be something intrisit to the model.

## Notes

Machine learning is about generalization garantee. 

In the regime where the network's learning capability is much greater than the 
dataset, the network can virtually learn any random function. Therefore 
conventional theories like VC dimensions does not distinguish between the two 
cases:
> 1. $F$ fitting an image classification function on input X, and perform well
    
and 
> 2. $F$ fits a random function on X, achieving close to random generalization error

This is why understanding generalization in deep learning requires new thinking (theory).

This regime can be reached as soon as the number of parameters exceeds the 
number of data points in training data. And we are usually in this regime in 
practice.

### intro

some neural networks generalize well, some don't. Normally if you have a model
with a large learning capability, you would think the generalization error would
also tend to be large because it overfits. However with a large number of 
parameters, deep learning networks generalize surprisingly well.

Existing learning theory does not offer an answer to this question. 
- VC dimention [^vapnik_1998], 
- Rademacher complexity [^Bartlett_Mendelson_2003]
- Uniform stability [^Mukherjee_2002][^Bousquet_Elisseeff_2002][^Poggio_2004]
- Regularization and early stopping being implicity regularization

[^vapnik_1998]: VC dimension

[^Bartlett_Mendelson_2003]: Radmacher complexity

[^Mukherjee_2002]: uniform stability

[^Bousquet_Elisseeff_2002]: uniform stability

[^Poggio_2004]: uniform stability


#### Randomization tests

used in this work comes from non-parametric statistics.

| model | train label | train error | generalization |
|  ---  | ----        | --------    | ------         |
| neural net | random | zero        | random guess   |
|       | image classification | small | small error |

#### Smooth Tuning
by smoothly varying the amoutn of noise, authors show network
can memorize training noise while still being able to extract remaining useful
signal. 

> Deep neural networks easily fit random labels.

#### Regularization
Explicity forms of regularization (weight decay, dropout, data augmentation) do
not explain this. 

> Explicit regularization may improve generalization performance, but is neither necessary nor by itself sufficient for controlling generalization error.

> Dave: L2 regularization prevents the networks from learning the random labels during
training. need to take a closer look

#### Implicit Regularization via SGD

SGD itself is a form of implicity form of regularization. Under SGD even 
non-deep learning models can generalize well. They tested gaussian kernel
machines. This doesn't explain why one architecture is better than the other,
but does sugguest that SGD itself calls for more investigation.

#### Expressivity over Finite Sample

Previous work on expressivity focuses on expressivity over entire domain. 
Authors instead forcuses on finite dataset. 

Also authors demonstrate shallow network (2 layer LeNet) can show large 
expressivity by simply increasing width.

## Other Notes
for MNIST, d<<n, model is linear in the "lifted feature space $f(x)$ where $f$ is a basis of the RKHS defined by the RBF kernel. This is called "kernelization".

## Implicit Regularization
Behnam Neyshabur
https://arxiv.org/pdf/1412.6614v4.pdf


