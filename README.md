# PPO_PONG_DISCRETE

Proximal Policy Optimization Algorithm applied to PONG in discrete environment.

[![Watch the video](/media/pong.gif)](/media/video.mp4)

**Author:**

*Simone Rossetti, Roma, January 2020*

**Framework:** 

PyTorch

**Abstract:** 

PPO algorithm is a new kind of policy gradient method for reinforcement learning, in which this kind of methods are an appealing approach because they directly optimize the cumulative reward and can straightforwardly be used with nonlinear function approximators such as neural networks.
PPO alternates between sampling data through interaction with the environment, and optimizing a surrogate objective function using stochastic gradient ascendent.
The algorithm shown in the picture below is a generic representation of a proximal policy optimization method.
Whereas standard policy gradient methods perform one gradient update per data sample, it proposes a different objective function that enables multiple epochs of mini-batch updates.

**Environment**

<p align="center" width="100%">
<img src="/media/sizes.png" alt="" width= '100%'/>
</p>

Pong environment is 210 x 160 x 3 pixel (H x W x C) in RGB (3 channels). 
There are 6 possible actions in this environment, only 3 are useful: ‘stay’ 0, ‘up’ 2 and ‘down’ 5.
To keep track of our environment the model needs consistent representation of the environment. Because of that, images have been reduced to a single channel (greyscale), then cropped along the playing area, squared and reduced by dimension. Resulting images of the states are 1 x 84 x 84 pixel (C x H x W).
Channels have been shifted with respect the axes because Convolutional Layers in PyTorch compute batch (B) of images in a different order (B x C x H x W).

**Top reward:**

Best Reward +21.000 in 4070 epochs (mean on 10 tests each 10 epochs)

<p align="center" width="100%">
<img src="/media/res.png" alt="" width= '50%'/>
</p>
