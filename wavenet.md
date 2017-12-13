[WaveNet: A Generative Model for Raw Audio](https://arxiv.org/pdf/1609.03499.pdf)
---

The power of dilated causal convolutions was brought to my attention during the Deep Learning tutorial at NIPS 2017.

### Summary
- Dilated causal convolutions preserve the ordering in which we model the data
- Parallel predictions at training time; sequential for prediction as each sample is fed back into the network to predict next
- Dilated causal convolutions allow very large receptive fields without requiring many layers or large filters (as would be the case without dilations)
- In WaveNet, dilation is doubled every layer up to a limit and then repeated, e.g. 1, 2, 4, ..., 512, 1, 2, 4, ..., 512, 1, 2, 4, ..., 512
- This gives exponential receptive field growth with depth (each 10-layer block from 1 to 512 has receptive field size 1024)
- Since audio is typically stored as 16-bit integers, they apply a non-linear compression transformation and quantise to 256 values
- Uses gated activation unit (as in PixelCNN), and residual and skip connections


- WaveNet has also been used for discriminative speech recognition ("With WaveNets we have shown that layers of dilated convolutions allow the receptive field to grow longer in a much cheaper way than using LSTM units.")
 
