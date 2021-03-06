# GAN_pytorch

## Reference Paper

**Generative Adversarial Nets** 

[Link to Paper](https://arxiv.org/pdf/1406.2661.pdf)

---

## References : 

The network architecture, and choice of activations and regularization units is inspired from different implementations available on web

For generator, leaky relu activations for all layers except the final output layer is used. Output layer has Tanh activation. 

For discriminator, leaky rely activations and dropout layer is used for all the layers except output layer. Output layer uses Sigmoid activation. 

--- 

## Training Data

MNIST train Dataset is used for training. 

--- 

## Network Details

GAN - Generative adversarial networks are implicit density type of generative models. The focus here is not to explicitly model the data distribution, but to sample from the data distribution directly. 

Few examples of explicit density models are [MADE](https://github.com/pranayKD/MADE_pytorch) and [pixelCNN](https://github.com/pranayKD/basic_pixel_cnn_pytorch)

GAN consists of Generator and Discriminator models. Both these models are pitted against each other. 

* Generator Network
  * Generator network tries to take data points from latent space and tries to create an image

* Discriminator Network
  * Discriminator network has only task to classify real image from fake image. Fake image is the one that is created by generator network. 



----
## Training Loss and Generated Images

* Epoch 1
<p float="left">
  <img src="Images/epoch_1_loss.png" width="300" /> 
  <img src="Images/epoch_1_digits.png" width="300" /> 
</p>

---
* Epoch 20
<p float="left">
  <img src="Images/epoch_20_loss.png" width="300" /> 
  <img src="Images/epoch_20_digits.png" width="300" /> 
</p>

---

* Epoch 100

<p float="left">
  <img src="Images/epoch_100_loss.png" width="300" /> 
  <img src="Images/epoch_100_digits.png" width="300" /> 
</p>

---

## Walking in latent space

Are Generative networks really learning the underlined data distribution and storing it in the latent space in case of GAN - is one of the major questions. To show that the GAN network is not simply memorizing the training data distribution, sometimes the L1 distanced k nearest neighbors are extracted from the training data for corresponding generated image, and based on the difference, it is concluded that generation is not because of the network memorizing training data. But it is not a reliable matrix. 

Often, a more reliable method is to walk in latent space and check if the transitions are smooth. 

Transition from 1 to 7 - 

<p float="left">
  <img src="Images/inter_1_7.png"  /> 
</p>

Transition from 5 to 4 - 

<p float="left">
  <img src="Images/inter_5_4.png"  /> 
</p>



----
