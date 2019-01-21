
# Deep Unsupervised Learning


## Autoregressive models

### Advantages
- Simple to use
- Easy to sample
- Reduce curse of dimensionality

### Disadvantages
- Generation is slow
- Highly order-dependent
- Teacher forcing: only learning to predict one step ahead, not many - potentially brittle generation, unable to generate long sequences, or myopic representations, e.g. for potential use in other tasks

### Examples
- Wavenet - 16kHz generation, but coherent over a long time
- PixelRNN - autoregressive applied to images; have to use an arbitrary ordering (e.g. raster scan)
  - N.B. both PixelRNN and Wavenet predict essentially a continuous variable, but use a softmax, discarding ordering of the classes, but still works better than e.g. Mixture Model
  - Clear local structure, clearer global structure when conditioning generation on a label
- Subsample pixel networks - change the order of the autoregressive predictions in PixelRNN - model each slice autoregressively, then model next slice conditioned on the previous one
  - Increases the size of image that can be generated
- Video Pixel Network (VPN)

## Representation learning
- How to generalise to new tasks?
- Deep networks learn complex, often hierarchical, representations of the data - an internal language to describe the data --> a functional language emerges from simple tasks
- How can a language emerge before there is a language to describe it - a functional language - Wittgenstein's language games 
- Distill paper - visual vocabulary, e.g. edges, orientations -> textures - > objects
- Task-driven representations are driven by the requirements of the task; should unsupervised learning actually give better representations? e.g. as long as laws of physics help to model observations in the world, they are worth representing (whereas they might not matter for 'simple' classification)
- How can we read the latent language of the network? 
  - Autoencoder - bottleneck to create reusable latent representations
  - Variational Autoencoder - information theoretic approach, what is the coding cost of representing the latent information
  - Associative Compression Networks (ACN) - a common problem with VAEs - the codes tend to get ignored in very powerful networks - amortising the code cost over the whole dataset
- How to evaluate how good representations are? Use a downstream task, e.g. MNIST linear classification on representations
- Mutual Information - 'describing well' == maximise mutual information
  - For an autoencoder, the reconstruction cost is a lower bound on the MI
- Contrastive Predictive Coding - prediction from a latent code (using noise-contrastive estimation)

## Unsupervised reinforcement learning
- Auxiliary tasks
- Intrinsic motivation
  - Curiosity - guiding to novel observations
    - "Compression progress" / Complexity Gain (Schmidhuber)
  - Empowered agents: mutual information between actions and resultant state, e.g. classify the 'option' that led to the final state?
  
  

