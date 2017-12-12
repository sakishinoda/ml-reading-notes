[Batch Renormalization: Towards Reducing Minibatch Dependence in Batch-Normalized Models](https://arxiv.org/pdf/1702.03275.pdf)
---

### Summary

- Corrects for a discrepancy in batch normalization between training and inference for small or non-i.i.d. minibatches while retaining the benefits of training efficiency and insensitivity to initialization of batch normalization
- Example non-i.i.d. setting for minibatches: choosing 16 random labels and two random examples for each for a size-32 minibatch
- Batch renormalization "ensures that the activations computed in the forward pass of the training step depend only on a single example and are identical to the activations computed in inference"
- Batch renormalization effectively uses the same mean and standard deviation for normalization as would be used during inference during training time
- Batch renormalization essentially augments batch normalization layers with an affine transformation -- I am a bit unclear about the details of what exactly the procedure is ("we treat the parameters *r* and *d* of this affine transform as fixed, even though they were computed from the minibatch itself")