### Modeling Rounding with Noise

KL divergence is on a conditional probability distribution

Noise vs. Roundng

Differential Entroy Vs. Discrete entropy

How to vary the level of compression?

VAE vs GAN, GAN learns the measure. 

Use to generate great images. Find a generator to generate new images.

Here we have a objective measure of performance. (size of image). GAN has no such
objective 

## Papers


- Super Resolution **Amortised Map Inference for Image Super-Resolution**, 
    Sonderby, Caballero, Theis, Shi, Huszar, ICLR 2017

    arxive | https://arxiv.org/abs/1610.04490#
   --- | ---
   pdf | https://arxiv.org/pdf/1610.04490.pdf     

- Training GANs **Towards Principled Methods for Training Generative Adversarial 
    Networks**, Arjovsky and Bottou, ICLR 2017

    Authors assump that discriminator is perfect. 
    
    Jensen-Shannon Divergence
    : when $P$ and $Q$ are close, JS divergence is infinitestimally close to $1$.
    : hence there is no gradient for the generator to follow.
    
        Softmax-Logloss for Binary Classification
        : two possible outcomes, with a softmax and a log-loss.
        : DC GAN was doing this already. use the **margin** as the loss.
        : An alternative Fix, use earth mover's distance to replace JSD.
-