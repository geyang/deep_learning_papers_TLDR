# Deep Learning Papers TLDR

My collection of notes on deep learning papers.

To take a look at some of my projects and notes on deep learning that's not directly related to literature research, go [here: @episodeyang/deep_learning_notes](https://github.com/episodeyang/deep_learning_notes#notes-on-deep-learning)

## Reading List (TODO)

I will keep this todo list short. This is what I'm working on this week.

### ICLR 2017 Best Papers

- [work in progress] "Making Neural Programming Architectures Generalize via Recursion"
by Jonathon Cai, Richard Shin, Dawn Song
https://openreview.net/forum?id=BkbY4psgg&noteId=BkbY4psgg
- "Semi-supervised Knowledge Transfer for Deep Learning from Private Training Data" 
by Nicolas Papernot, Martín Abadi, Úlfar Erlingsson, Ian Goodfellow, Kunal Talwar
https://openreview.net/forum?id=HkwoSDPgg&noteId=HkwoSDPgg


## Table of Contents 

### ICLR 2017 Best Papers

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

