[Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation](https://arxiv.org/pdf/1708.05144.pdf)
---

See also the [OpenAI blog post](https://blog.openai.com/baselines-acktr-a2c/) on the ACKTR and A2C Baselines implementation.

### Background
- Aim: Improve convergence, training speed and sample efficiency using natural gradient optimisation
- Natural gradient computation requires inversion of the Fisher information matrix
- Trust-region policy optimization (TRPO) avoids explicitly storing and inverting Fisher matrix by using Fisher-vector products
- However, TRPO requires many steps of conjugate gradient for a single parameter update, and many samples per minibatch for accurate curvature
- Kronecker-factored approximated curvature (K-FAC) is a scalable approximation to natural gradient, using an update comparable in cost to an SGD update (unlike TRPO) and a running average of curvature (enabling small batches)

### This work
- AKCTR uses Kronecker-factored approximation to natural policy gradient to allow covariance matrix of gradient to be inverted efficiently
- Per-update computation cost of ACKTR is 10-25% higher than SGD-methods
- *Implementation details which make me think I need to read up on PG methods in general and A2C in particular.*

### Findings
- Yep: better sample efficiency and higher rewards
