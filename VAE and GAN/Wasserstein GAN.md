Key Topics:
- The mode dropping phenomenon
- Integral Probability Metrics (IPMs)
- kernel trick in Maximum Mean Discrepancy (MMD)
- 

## Ideas:
can we combine EM loss and KL divergence, to fine tune a model in the terminal stage by making the loss more steep in the middle?

equivalently, we can use a EM loss with larger step size.


## Todo

- http://www.alexirpan.com/2017/02/22/wasserstein-gan.html
- read about professor forcing.
- https://zhuanlan.zhihu.com/p/25071913
- https://www.zhihu.com/question/52602529/answer/158727900
- 

而改进后相比原始GAN的算法实现流程却只改了四点：

- 判别器最后一层去掉sigmoid
- 生成器和判别器的loss不取log
- 每次更新判别器的参数之后把它们的绝对值截断到不超过一个固定常数c
- 不要用基于动量的优化算法（包括momentum和Adam），推荐RMSProp，SGD也行

A three paper series: 
- theory paper why GAN 
- Wesserstein GAN
- Improved training for WGAN

Someone eles' paper
- BEGAN

Variable compressi