# Deep Learning Papers TLDR [![](https://img.shields.io/badge/link_on-GitHub-brightgreen.svg?style=flat-square)](https://github.com/episodeyang/deep_learning_papers_TLDR)

My collection of notes on deep learning papers.

To take a look at some of my projects and notes on deep learning that's not directly related to literature research, go [here: @episodeyang/deep_learning_notes](https://github.com/episodeyang/deep_learning_notes#notes-on-deep-learning)

## Reading List (TODO)

I will keep this todo list short. This is what I'm working on this week.

### Bayesian Optimizations

Closely related to statistical ideas of [¹]
- **optimal design of experiments**, dating 
back to Kirstine Smith in 1918. 
- **response surface methods**, they date back to Box and Wilson in 1951. 
- **Bayesian optimization**, studied first by Kushner in 1964 and then
Mockus in 1978. 

Methodologically, it touches on several important machine learning areas: 
active learning, contextual bandits, Bayesian nonparametrics 
- Started receiving serious attention in ML in 2007, 
    - Brochu, de Freitas & Ghosh, NIPS 2007 [preference learning]  
    - Krause, Singh & Guestrin, JMLR 2008 [optimal sensor placement]  
    - Srinivas, Krause, Kakade & Seeger, ICML 2010 [regret bounds]  
    - Brochu, Hoffman & de Freitas, UAI 2011 [portfolios] 
- Interest exploded when it was realized that Bayesian optimization provides an
excellent tool for finding good ML hyperparameters.

[¹]: https://www.iro.umontreal.ca/~bengioy/cifar/NCAP2014-summerschool/slides/Ryan_adams_140814_bayesopt_ncap.pdf

### ICLR 2017 Best Papers

- "Semi-supervised Knowledge Transfer for Deep Learning from Private Training Data" 
by Nicolas Papernot, Martín Abadi, Úlfar Erlingsson, Ian Goodfellow, Kunal Talwar
https://openreview.net/forum?id=HkwoSDPgg&noteId=HkwoSDPgg

### Attention

- [link](https://www.dropbox.com/s/h6qmhhq3kpfhbzd/L10%20attention.pdf?dl=0)


## Table of Contents 

### ICLR 2017 Best Papers

- [**Notes on** "Making Neural Programming Architectures Generalize via Recursion"
by Jonathon Cai, Richard Shin, Dawn Song"](ICLR%202017/Making%20Neural%20Programming%20Architectures%20Generalize%20Via%20Recursion.md) **Berkeley**
    
    Authors propose to augment neural networks by a key abstraction: recursion. 
    Work applied this idea to Program-Interpreter from [Reed & de Freitas] 2006, 
    and demonstrates superior generalizability, tractability with proven 
    garantee.
    
    Recursion greatly reduces the domain of each neural program component, also
    greatly reduces the amount of training data required, and make it easier to
    interpret and validate.

    [Reed & de Freitas]: https://arxiv.org/abs/1511.06279

- [**Notes on** "Understanding deep learning requires rethinking generalization"](ICLR%202017/Understanding%20deep%20learning%20requires%20rethinking%20generalization.md) **Google Brain**
    
    Through experimentation, authors shows how traditional 
    approaches to generalization failes to explain why large neural networks 
    generalize well in practice. They also explains why deep learning requires
    rethinking generalization. 

### Neural Compression and Techniques

- 2005, Han et al., **Deep compression: Compressing deep neural networks with pruning, trained quantization and huffman coding** [[pdf]](https://arxiv.org/pdf/1510.00149.pdf)
    
    **gist**: A three stage pipeline:
    1. zero out small weights (prunning) 9x-13x
    2. Trained Quantization 27x-31x
    3. Huffman Encoding 35x-49x
    
    without suffering any loss in accuracy.

- ICLR 2017, Han et al., **Dense-Sparse-Dense Training for Deep Neural Networks** [[pdf]](https://arxiv.org/pdf/1607.04381.pdf)
    
    **gist**: Sparse training and dense retrian improves network performance
    1. train normally 
    2. mask out small weights (bimodal distribution), then retrain
    3. remove mask and set small weights to zero, then retrain.
    
    **profit**: 1~2% abs. imprv. across vision, speech and caption tasks, 4~13% rel. imprv.
## Sources

The source of this repo is mostly:
- various online reading lists
- Conferences
- Courses: this is probably the most important source because they are structured
- friends and colleague's recommendations

## Other Repos

My lab-mate [Nelson](https://github.com/nelsonleung)'s notes can be seen [here](https://github.com/nelsonleung/deep-learning-papers-reading-notes).

