---
URL: https://www.youtube.com/watch?v=F1ka6a13S9I
---
# Nuts and Boltz of Applying Deep Learning
## Trends in AI

- traditional AI plateu. "SVM guys were more motivated in feature engineering"
- DL got *more data* and *larger*
- In production team, both AI and HPC specialties are needed.

## AI research buckets
- Geral DL: fully-connected layers
- 1D Sequence Models: LSTM, GRU
- 2D/3D CNN
- Other: Unsupervised Learning, Reinforce learning, Sparse Coding, ICA

First three buckets capture 99% of all industry applications. The fourth should 
be the future.

## End-to-end DL

movie review -> sentiment
image -> object, integers

more complex outputs
image -> caption | vindal, shuwei from Baidu

speach recorgnition -> output audio transcript
Alex Graves

But End-to-end DL is not the solution for everything. Nice because learns features.

*Speach*: 
audio -> phonemes -> transcript
audio --neural net--> transcript

reall upsets lots of people. "phonemes are illusions of linguistists and really 
shouldn't exist" -- Ng

Need $(x,\,y)$. 

Imaging want to use X-ray of hand to predict age of child.

Traditional algo: get input -> get bones -> measure -> age (non-end to end)
end-to-end: x-ray -> age

Problem: not enough data, traditional algo is better.

image -> cars        -> trajectory -> steering
      -> pedestrians ->
      
image -> steering

Goal: Build human-level speech system

**use cross-validation**. Train, dev (validation), test.

type              | value |||
              --- |--- | ---        | ---
Human-level error |1%  |
training set error| 5% | `bias`     | train bigger model 
dev set error     | 6% | `variance` | add regularization, early stopping, or more data.

1. is your training error `high`?
    - bigger model
    - train longer
    - new model architecture
2. is validation error `high`?
    - "high varianve problem":
    - more data
    - add regularzation
    - new model architecture
3. Done.

The coupling between `bias` and `variance` is weaker. Can always train a bigger model, don't necessarily have to trade `bias` for `variance` or the other way around. 

## Automatic Data Synthesis

- OCR: data synthesis require care, naive aproach don't work. 
- Speech Recognition: Car noise
- NLP: un-grammatical sentence, have attention network correct it automatically.
- video games: (RL) 20 cars from GTA is not enough. 

Unified data warehouse

user access rights, but all data should be inside a unified data warehouse.

## Cross-validation

70%/30% split

## Rethink Bias and Variance

want to launch new product: speach-enabled rear-view mirror. 

50, 000 hr of data, but not in-car. 
10 hr of data for rear-view mirror scenario. 

What do you do?

Best idea: develop-set and test-set from the same distribution.

non-RR 49,980hr -> train
non-RR 20 hr -> Train-Dev
RR 5 hr -> Dev
RR 5 hr -> Test set

Generalization of the bias/variance concept.
source       | error      | error
         --- | ---        | ---
Human Level  | 1%         | 1%
Training set | 10%        | 1%
Training-dev | 10%        | 2%
Dev          | 10%        | 2.1%
test set     | 10%        | 10%
             | large bias | over-fit Training Dev
             
bias, variance, train-test mismatch, overfitting of dev

## Why is human-level porformance such a big deal?

quickly superceed human performance, then improvement gets much harder. 
- label comes from humans.
- distance between neural net to human brain is far
- satisfied and bored

Some theoretical limit: noisy, blurry, impossible to figure out

**Optimal Error Rate**/**Bayse Rate**
: Optimal algorithm can not do better than this.

- Humans are pretty good at voice-recorgnition, and image-recognition.
- While worse than humans, have good ways to make progress.
    - labels from humans
    - easy to Error Analysis
    - easy to estimate bias/variance effects
    
        image-recognition task: training error, dev error is 10%. 
        if human is 8%, then you have variance problem. On the other hand if human is 1%, then you have bias problem. Human performance is a proxy for Bayes Rate. Once you exceed human-level performance, you can find subsets of data where you are still worse than human (like an accent). 


## How do you define human-level performance?

#### Medical Example

1. Typical human 3%
2. Typical doctor 1%
3. Expert doctor 0.7%
4. Team of Expert Doctors 0.5%

Last is the best definition of "human-level" performance for the purpose of driving machine learning algorithms. We are using "human-level" performance as a proxy of the optimal error rate.

## Product Processes

What can AI/DL do?

We invent new processes as AI gets better and better. 

It is helpful to know what you can design and what you can not.

- Assume AI can do absolutely anything that a person can do
    with less than 1 second of thinking, a neural net can do it (perception, speech recognition, image recorgnition).
- predicting outcome of next in sequence of events.

## Learning Curve in machine learning

- ML course
- DL school
- Kaggle

#### **One Ph.D. process extremely powerful**
1. Read a lot of papers,
2. work on replicating results

You will have new ideas that pushes the state-of-the-art. 20/50 papers later, you will start to have your own ideas. 
 
3. Dirty work: going on the internet, download, clean data, debugging stack trace, hacking GPU kernel, reading a paper and struggling at replicating the result.
4. Only Dirty work: fails too. 

**You need to do all of the above**.

No reward next weekend "The Saturday Story".

