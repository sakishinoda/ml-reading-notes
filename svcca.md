[SVCCA: Singular Vector Canonical Correlation Analysis for Deep Learning Dynamics and Interpretability](https://arxiv.org/pdf/1706.05806.pdf)
---


### SVCCA

- SVCCA combines Singular Value Decomposition and Canonical Correlation Analysis
- SVCCA can be used to analyse deep representations
- Each neuron is represented as an activation vector, a map of input datapoints to scalar outputs, a single neuron's response over the entire dataset
- Representing neurons by their activation vectors in R^m where m is the size of the dataset defines the layer as the vector subspace spanned by the activation vectors of the neurons
- SVCCA allows comparison of each neuron's activation vector against all other activation vectors in layer
- SVCCA can be used to find the layer subspace
- The paper introduces some clever discrete Fourier transform techniques to do fast SVCCA on convolutional layers

### Applications
- SVCCA used to study learning dynamics of neural networks show that convergence broadly occurs bottom up; this means freezing layers progressively from the bottom up during training can reduce overfitting
- Devising clever schedules for layer freezing is left to future work
- SVCCA used to show when an architecture becomes sensitive to classification of different accuracies




