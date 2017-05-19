Google Deepmind
| Authors                       | arxiv                            |
| -------                       | -------------------------------- |
| Scott Reed, Nando de Freitas  | https://arxiv.org/abs/1511.06279 |

## Constituents

- task-agnostic core
- key-value program memory
- domain-specific encoders

> Interacting with media naturally involves making a sequence of taking an action, observing, and taking more actions. This creates a major challenge: how do we learn which actions to take? That sounds like a reinforcement learning problem and we could certainly take that approach. But the reinforcement learning literature is really attacking the hardest version of this problem, and its solutions are hard to use. The wonderful thing about attention is that it gives us an easier way out of this problem by partially taking all actions to varying extents. This works because we can design media — like the NTM memory — to allow fractional actions and to be differentiable. Reinforcement learning has us take a single path, and try to learn from that. Attention takes every direction at a fork, and then merges the paths back together. [^1]



[^1]: http://distill.pub/2016/augmented-rnns

