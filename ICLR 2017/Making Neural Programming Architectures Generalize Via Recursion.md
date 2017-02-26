# Making Neural Programming Architectures Generalize Via Recursion

## TLDR;

Recursion allow Neural Programs to devide and conquer a problem, and generalize
indefinitely. By devide and conquer, each neural program component has a much 
reduced domain, making interpretations easier and training faster.

key words | neural program, recursion, provable garantee
---- |:---
openreview | https://openreview.net/forum?id=BkbY4psgg&noteId=BkbY4psgg
pdf | https://openreview.net/pdf?id=BkbY4psgg

- [tail recursion](https://www.quora.com/What-is-tail-recursion-Why-is-it-so-bad)
    is equivalent to a loop.

## Future Directions

- offer more tasks beyond the four covered here
- **decrease supervision**, perhaps partial or non-recursive traces
- **new Neural Programming Architecture** that integrates a notion of recursion
    within the model.


## Summary 

This paper builds on top of [Reed & de Freitas]' 2016 work on Neural
Program-Interpreter (NPI), and uses the same architecture to show that recursion
can fundamentally solve the generalization problem that plagues neural programs,
while also providing clear path for provability. The authors argue that poor
generalization performance of prior work is an important problem. Future
neural programs need to be able to generalize well, from limited set of training
data, and learn quickly. This is especially important (and difficult)
considering that the space for potential solution is large.

[Reed & de Freitas]: https://arxiv.org/abs/1511.06279

The experiment concerns mostly
1. the model (the NPI machinery)
2. the training process (SGD from input/execution trace)

The training process distinguishes this work from most of prior NP literature
and is the same as [Reed & de Freitas]. Trainings sets is very small, and for
the verification section it was further reduced to make a point.

              model        | traning set     
              ---          | ------         
     grade school addition | 200 traces 
     bubble sort           | 100 traces 
     topological sort      | 1 trace for a graph of 5 vertices
     quick sort            | veries

This paper show cases four test problems: (sect. 3.2, page 6)
- grade school addition
- bubble sort
- topological sort
- quick sort

Recursion allows the authors to verify the validity of the neural programs by:
1. proving the finite base cases
2. proving the reductions
3. demonstrate proper termination

Importance of recursion is also demonstrated by implementing with partially
recursive networks. Performance contrast is stunning (ref. Table 1, 2, and 3, 
test are all done on 30 randomly selected DAGs. Table 1. reproduced here for 
bubble sort.)

     Length of Array | Non-Recursive | Partially Recursive | Full Recursive
     :-------:       | :-------:     | :-----:             |  :----:
     2               | 100%          | 100%                | 100% 
     3               | 6.7%          | 23%                 | 100% 
     4               | 0             | 10%                 | 100% 
     8               | 0             | 0                   | 100% 
     20              | 0             | 0                   | 100% 
     90              | 0             | 0                   | 100%


Section 3.2 and 3.3 details the recursive formulations for these problems and 
the general approach to provable generalization. Seciton 4 covers the experiment
result and offers the proofs.

## Background: Generalization Task Failures in Prior Work

#### Problems


- **poor genralization performance**  
    Current system demonstrate poor generalization beyond certain level of 
    complexity.

- **no provable garantee**  
    memory operation in NPI is complex and untractable, can not prove the general 
    behavior of network beyond what's in the sample.

We need a way to solve all these problems.

#### Curriculum Learning Doesn't Solve These Issues

- Nando Paper: bubble sort task [fails when it gets complex]
- Zeramba et al., single digit multiplication
- Graves et al., graph tasks (2016)

#### Recursion

- allow provable garantee of neural programs' behavior without need of
exhaustive enumeration.


## References

1. Marcin Andrychowicz and Karol Kurach. **Learning efficient algorithms with 
hierarchical attentive memory**. CoRR, abs/1602.03218, 2016. 
URL http://arxiv.org/abs/1602.03218. 

2. Alex Graves, Greg Wayne, and Ivo Danihelka. **Neural turing machines**. 
CoRR, abs/1410.5401, 2014. URL http://arxiv.org/abs/1410.5401.

3. Alex Graves et al., **Hybrid computing using a neural network with dynamic 
external memory**. Nature, 538 (7626):471–476, October 2016. 
doi: 10.1038/nature20101. URL http://www.nature.com/doifinder/10.1038/nature20101.

4. Lukasz Kaiser and Ilya Sutskever. **Neural gpus learn algorithms**. 
CoRR, abs/1511.08228, 2015. URL http://arxiv.org/abs/1511.08228.

5. Karol Kurach, Marcin Andrychowicz, and Ilya Sutskever. 
**Neural random access machines**. ERCIM News, 2016(107), 2016. 
URL http://ercim-news.ercim.eu/en107/special/neural-random-access-machines.

6. Arvind Neelakantan, Quoc V. Le, and Ilya Sutskever. 
**Neural programmer**: Inducing latent programs with gradient descent, 2015.

7. Scott Reed and Nando de Freitas. **Neural programmer-interpreters**. 
ICLR, 2016.

8. Oriol Vinyals, Meire Fortunato, and Navdeep Jaitly. 
**Pointer networks**. URL http://papers.nips.cc/paper/5866-pointer-networks.

9. Wojciech Zaremba, Tomas Mikolov, Armand Joulin, and Rob Fergus. 
**Learning simple algorithms from examples**. ICML 2016, June 19-24, 2016,
URL http://jmlr.org/proceedings/papers/v48/zaremba16.html.