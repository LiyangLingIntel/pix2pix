# pix2pix

[TOC]

###  Datasets:

<https://people.eecs.berkeley.edu/~taesung_park/CycleGAN/datasets/>

### Reference:

* <http://sse.tongji.edu.cn/linzhang/CV/ReadingMaterials/Image-To-Image_Translation.pdf>
* <https://arxiv.org/pdf/1703.10593.pdf>

## Proposal

### 1. Background

In the image processing domain, the targets of many problems are always to convert one input image to its corresponding output image, like the transformation among greyscale image, gradient image and coloured image. Generally, specified algorithms will be applied for different question. For example, when using CNN to solve the problem of image translation, it's needed to define the loss function for the optimization of each problem. A common solution is to narrow down the Euclidian distance between input and output data by training CNN, while the fuzzy output would be get for the most situations. 

The essence of these issues is just constructing the mapping between pixels to pixels. So, based on the theory of GAN(Generative Adversarial Network), pix2pix, as a common method was raised to solve these problems.

### 2. Related Work

Basically, we metioned Generative Adversarial Network, from which we can genarate target images by feeding in some dummy input data. However, traditional GAN is not powerful enough to solve all of our image processing tasks, below we conclude two drawbacks of GAN.

* Lack of user control abilities. Which means user could not specify the details of outputs during training and testing, except for adjusting the training dataset.
* For the most situation, basic GAN could not generate images with high quality. Even if the output image looks pretty good, it would be vague when zooming in because of low resolution.

To improve the effects of GAN, there are several methods are developed. 

First one is pix2pix, it made a small modification on traditional GAN. Instead of using random noise as input data, pix2pix use paired image to train the neural network to learn the relational mapping. So that user can specify the shape, colour or other attributes of output images.

Another one is CycleGan which is more complex method, because there is no need to use paired data, it can be workable with just a set of input data and a set of output data. The success of CycleGAN is it could seperate the content and style by applying some constraints into training steps, so that the  whole model could be more flexible.

### 3. Our Work



