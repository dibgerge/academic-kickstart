+++
title = "Tensorflow, PyTorch, and MxNet"
subtitle = "An experimental and subjective comparison"

date = 2019-03-11T00:00:00
lastmod = 2019-03-11T00:00:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Admin"]

tags = ["deep learning"]
summary = "Comparison of three deep learning frameworks."

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
# projects = ["internal-project"]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

  # Show image only in page previews?
  preview_only = false

# Set captions for image gallery.
+++

In the past 2 years, I have been exclusively using Tensorflow with Keras for training and testing deep neural networks. I never really thought twice about it, because this is what everyone else seems to be using. I mean, just looking at the popularity of those frameworks in github compared with their closest competitors was enough to make the decision for me. Here are the approximate statistics as of March 2019 for the four most popular frameworks.

|             | [Tensorflow](https://github.com/tensorflow/tensorflow) | [Keras](https://github.com/keras-team/keras) | [Pytorch](https://github.com/pytorch/pytorch) | [Mxnet](https://github.com/apache/incubator-mxnet) |
|-------------|------------|-------|---------|-------|
| Github <i class="fas fa-star"></i>| 122,500    | 39,000| 25,500  | 16,500|

Recently, I have been going through the lectures of [Jeremy Howard's Fast.ai](fast.ai) excellent class, where they use Pytorch as the backend of the high-level library they built. This was one of the reasons I started questioning what was I missing by limiting myself to Tensorflow. Also, I have seen the extensive vision library of [MxNet's GluonCV](https://gluon-cv.mxnet.io/index.html), and this really made me feel that I might be missing out.

In addition to all the fear of missing out stuff, I was coding my own implementation of [ResNet](https://gluon-cv.mxnet.io/index.html), and I scoured online the plethora of different implementations of ResNet, some with lots of <i class="fas fa-star">s</i>. I realized that many had implementation details which differed from the original paper, and it was not clear if it is intentional or not. Thus I really though that a test in reproducibility is due and so I did.

I set out to compare the three frameworks: tensorflow, pytorch, and mxnet. I wanted to use some of the built-in convolutional neural networks with built-in pre-trained weights to directly classify Imagenet's validation dataset images. Throughout this comparison, I was looking for three factors:

1. Ease of loading the dataset and reproducing the pre-processing steps required before feeding images to the neural network for classification.
1. Computed error rate vs framework's reported error. It would be also nice to compare the results with the original publication, but most report validation error using 10-crops, and here we use only single crop.
1. Inference speed.

## Dataset and Convolutional Neural Network Architectures
The datatset I used was Imagenet's validation dataset which constitutes of 50,000 images with different sizes. The easiest way to get your hands on the data is to download it from Kaggle [here](https://www.kaggle.com/c/imagenet-object-localization-challenge).

For the frameworks, I used the following versions:

- **Tensorflow 1.13** with Keras as the front-end interface (Note this is different from using Keras with Tensorflow backend since now Tensorflow comes packed with its own Keras version, which is not compatible with other frameworks).
- **PyTorch 1.0.1** with PyTorch vision for convolutional neural networks implementations
- **MxNet 1.4** with GluonCV for convolutional neural networks implementaitons

For the convolutional neural network, I considered four different architectures: [ResNet50](https://arxiv.org/abs/1512.03385), [Resnet101](https://arxiv.org/abs/1512.03385), [Mobilenet](https://arxiv.org/abs/1704.04861), and [Densenet121](https://arxiv.org/abs/1608.06993).

The top 1 error published on each frameworks' website, based on a single center crop evaluation is as follows:

|             | [Tensorflow (Keras)](https://github.com/keras-team/keras-applications) | [Pytorch](https://pytorch.org/docs/stable/torchvision/models.html) | [Mxnet (GluonCV)](https://gluon-cv.mxnet.io/model_zoo/classification.html) |
|-------------|------------|---------|-------|
| Resnet50    | 25.10      | 23.85   | 22.64 |
| Resnet101   | 23.60     | 22.63   | 21.66 |
| Mobilenet   | 29.60      | N/A     | 26.72 |
| Densenet121 | 25.0       | 25.35   | 25.03 |

We note here that the error for Resnet101 is reported in Keras Applications, but Resnet101 is not packaged with Tensorflow 1.13, which is used in this experiment, and thus we won't have any results for it. Also, Pytorch does not come packaged with an implementation of Mobilenet.

Also, it is interesting to see that especially for Resnet implementations, it is obvious that the accuracy of Mxnet > PyTorch > Tensorflow.

## Experiments

All the code used here can be found on [github](https://github.com/dibgerge/blog-tf-mxnet-pytorch). The biggest challenge here really is loading and pre-processing the images the right way. The following briefly describes how I did it for each of the three frameworks. 

### Tensorflow pre-processing

Uses the `Sequence` abstract class for loading the data using a a generator. The pre-processing pipeline is as follows:

1. Resized the shorter side of the image to 256 pixels (implemented manually).
2. Center cropped the image to 224 x 224 pixels (implemented manually).
3. Apply the function `preprocess_input` which applies the appropriate normalization based on how the network is trained. This function is provided with each different architecture built-in Tensorflow's Keras frontend.

### Pytorch pre-processing

Used the `Dataset` and `Dataloader` interfaces to feed the data to the neural network. The standard pipeline for pre-processing images for all architectures is documented and is a composition of four transforms using Pytorch's `transforms` API:

1. Resize image to 256 pixels (using `transforms.Resize`)
2. Center image to 224 pixels (using `transforms.CenterCrop`)
3. Convert images to pytorch tensor (using `transforms.ToTensor`)
4. Normalize image by mean subtraction and standard deviation scaling (using `transforms.Normalize`). The normalization values are given in the Pytorch's documentation.

### Mxnet pre-processing

Used the `Dataset` and `Dataloader` interfaces to feed the data to the neural network. Mxnet comes packaged with a preset function which applies the required pipeline for models pre-trained on imagenet, using the `gluoncv.data.transforms.presets.imagenet.transform_eval` function.

### Results

The following table summarizes the achieved error percentages for each of the four architectures using the three different frameworks.

| (% error)   | Tensorflow | Pytorch | Mxnet |
|-------------|------------|---------|-------|
| Resnet50    | 26.92      | 23.87   | 22.64 |
| Resnet101   | N/A        | 22.63   | 21.60 |
| Mobilenet   | 29.91      | N/A     | 26.73 |
| Densenet121 | 26.69      | 25.57   | 25.10 |

Interestingly, although I had the most experience with Keras, I could not reproduce the published results for Resnet and Densenet. This is probably because I had to manually implement the image resizing and cropping, which might be different one used to generate the published results. On the other hand, Pytorch provides the required documentation to be able to reproduce the results very closely. MxNet takes it even a step further by providing a single function which applies all required pre-processing, and the results match very well with published ones.

As for running times, I measured the total running time for classifying 50,000 images.  All predictions were made on GPU (Nvidia GTX 1080 Ti), while the image pre-processing was made on CPU. The following tables summarizes the running time results in seconds. **Please take those results with a huge grain of salt, since times vary a lot when loading and reloading large data from disk**:

| (seconds)  | Tensorflow | Pytorch | Mxnet |
|------------|------------|---------|-------|
| Resnet50   | 137        | 119     | 140   |
| Resnet101  | N/A        | 159     | 214   |
| Mobilenet  | 82         | N/A     | 118   |
| Densenet121| 173        | 120     | 195   |  

First, those results are somehow unfair to tensorflow. This is because I used threading with 4 workers for pre-processing images in Tensorflow, while 4 workers with multiprocessing was used for MxNet and Pytorch. But, this is rather Tensorflow/keras fault due to a [bug](https://github.com/keras-team/keras/issues/10855) not allowing me to use multiprocessing. Also, for Mxnet and Pytorch I measured the average time it took to classify 10 images (the batch size used). I did not do this in Tensorflow, because there is no easy way to measure per-batch times.

| (milliseconds)| Tensorflow* | Pytorch         | Mxnet            |
|------------|------------|--------------------|------------------|
| Resnet50   | N/A        | 6.7 $\pm$ 4.3      | 12.1 $\pm$ 1.9   |
| Resnet101  | N/A        | 11.8 $\pm$ 1.2     | 21.0 $\pm$ 3.2   |
| Mobilenet  | N/A        | N/A                | 6.7 $\pm$ 1.5    |
| Densenet121| N/A        | 15.6 $\pm$ 1.7     | 26.7 $\pm$ 3.7   |

Most of the time here is being spent loading the data from disk, and the GPU is not fully utilized. For example, based on average inference of 10 images in Resnet50, it takes about 33.5 seconds to classify all 50,000 images using PyTorch and about 60.5 seconds using Mxnet. We can reduce total inference by more than half if the GPU is kept busy.
Thus, the importance of handling data appropriately if speed matters.

## Who is the winner?

I think this experiment allowed me to assess three things:

* **Availability of pre-trained networks**: trophy goes to *Mxnet*. The extensive vision library of architectures/preset image processing is very impressive. Jury still out on other domains (RL, NLP). Tensorflow is a second, and Pytorch did not have much architecture packaged with it.

* **Reproducibility**: Again, trophy to *Mxnet*, with PyTorch a close second. I could not reproduce Tensorflow's results, and it is not clear how to do it using the documentation.

* **Data preparation**: a tie with *Mxnet and Pytorch*. Both frameworks use very similar `Dataset` and `Dataloader` interfaces. I was able to get going using this interface very fast. Keras also has a very similar interface using `Sequence` class, but the absence of something similar to `Dataloader` results in having to return batches rather than simply one image at a time. Also Tensorflow has a `Dataset` interface which I used before but somehow made me feel I am programming in C all over again.

* **Speed**: *Pytorch*. It is very obvious that Pytorch won the speed race all over the board. Also, although there is no information for only inference time in Tensorflow, it looks like Tensorflow also has the edge on Mxnet.

After this quick experiment, I am really excited about working with Mxnet and see how it goes. It looks like a great choice for working with computer vision, even though those experiments show it is the slowest. I am excited to see if it is really worth ditching Tensorflow for it, as I test it for different deep learning applications.

<a class="fab fa-github-square" href="https://github.com/dibgerge/blog-tf-mxnet-pytorch">Get the code!</a>
