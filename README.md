# Autoencoder Traffic Sign Images Compression

Convolutional autoencoder reducing [traffic sign images] to 1/6 of their original size.

---

## Problem Overview

Data compression has been an important task since the beginning of memory-based computers. With memory components being very limited in both size and speed, being able to make data occupy less space and buffer size was always in high demand. This issue still survives to this day, even with devices being able to store terabytes of data. Data has become more detailed, more complex. People now are more interested in more complex and unstructured forms of data, like images.

Image compression has many use cases, from data storage to more responsive web-based interfaces. Recently, another use case has gained attention: image compression to increase machine learning models' performance. Some models need to process data in real time with no delay, like the ones used in self-driving software. Being able to recognize traffic signs on road plates is fundamental for these models. They need to classify traffic signs as fast as possible so that there is more time available to make decisions and control the vehicle.

The [German Traffic Sign Recognition Benchmark] (GTSRB) has a collection of more than 50,000 traffic sign images from 43 different classes. Each class represents a specific traffic sign. Being a real-world database, with images having the low quality and bad lighting, this dataset has become a standard in designing models that can work in real-world, uncontrolled environments. Next, there are some of these traffic sign images:

![autoenconder_compressing_traffic_signs_grid](https://user-images.githubusercontent.com/33037020/198383273-691d99aa-dd77-46d6-af1a-c3ff87f7dfce.PNG)

## Analysis Introduction

[Autoencoders] are algorithms (neural networks) capable of capturing the most important features of data to later reduce data size or dimensionality. These two steps that autoencoders take have opened many applications for them: dimensionality reduction, denoising, outlier detection, data compression and others.

[Convolutional neural networks] (CNNs), on the other hand, are neural networks that combine image processing and machine learning techniques. With this combo, it is possible to process images with great accuracy, efficiency and generalizing capabilities. This type of neural network has evolved through the years and been implemented in many machine learning libraries. The combination of autoencoders and CNNs has become practical in autoencoder architectures with convolutional layers.

In this project, we aim to compress traffic sign images down to 1/6 of their original size. However, there is a condition that needs to be met: once decompressed, the images must be understandable. Considering the low dimensionality of these images (32 x 32) and their overall poor quality, we have designed a convolutional autoencoder able to compress them without losing important information.

Our autoencoder combines convolutional layers, extracting the most relevant information from the images, with average pooling layers reducing image dimensionality. At the end of the compression phase, the image was taken from 32 x 32 x 3 (height x width x channels) down to 8 x 8 x 8 (height, width, feature maps). Later, we decompress the image using transposed convolutions that can recover both image dimensionality back to 32 x 32, as well as features maps back to the starting 64.

In the next image grid, we show a comparison between the original images and their **decompressed versions, after going through the autoencoder**:

![autoenconder_compressing_traffic_signs_grid_decompressed](https://user-images.githubusercontent.com/33037020/198383297-690ae1a7-15a8-457f-851c-eb8cfe545da8.PNG)

[//]: #

[traffic sign images]: <https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign>
[German Traffic Sign Recognition Benchmark]: <https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign>
[autoencoders]: <https://en.wikipedia.org/wiki/Autoencoder>
[convolutional neural networks]: <https://www.ibm.com/cloud/learn/convolutional-neural-networks>
