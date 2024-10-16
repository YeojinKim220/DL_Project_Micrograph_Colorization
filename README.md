# Deep Learning Project - Micrograph Colorization
**Colorizing Electron Microscope Images Using CNN**

----------------------------

## Table of Contents
- [Introduction](#introduction)
- [Example Images](#example-images)
- [Datasets](#datasets)
- [Pre-training Model](#pretraining-model)
- [Training Model](#training-model)
- [Citation](#citation)

----------------------------

## Introduction [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/17pEFfrJtRwirtsoqRbf-IiUF2LG4eXvr) 

Did you know that the electron microscope images of the coronavirus commonly seen in news articles or newspapers are originally black and white? Due to the nature of using electron beams, electron microscope images are inherently black and white, so these images are colorized using Photoshop for better visualization. 

In this project, instead of using Photoshop, I applied deep learning to colorize electron microscope images. 

You can test the model by inputting an image URL, and it will colorize the image using the trained model. [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1H1A78ZW90MhNQgFCAFcW3S8RR1FpQanp?usp=sharing) 

## Datasets
- Pre-training: [MIT Places](http://places.csail.mit.edu/) - 41,000 images of landscapes and buildings
- Training: [Micrograph Image DataSets (color)](https://drive.google.com/file/d/1Jd9RmimqICSzJDTbpk94BZQmdDKfoskh/view?usp=sharing) - 4,845 microscope cell images collected using Google Image Crawling

## Example Images
![example_image_1](https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/example_image_1.png?raw=true)

## Pretraining Model [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1J_kLfx5d0VWTJZDehBXU9_VAcVRoAPFV?usp=sharing) 
Since the dataset of microscope images obtained via data crawling was relatively small, transfer learning was applied to compensate for this. The process involved pre-training the colorization model using a larger dataset of landscape images. 

Pre-training was performed using 41,000 images of landscapes and buildings from the [MIT Places](http://places.csail.mit.edu/) dataset. 

A convolutional neural network (CNN) with ResNet-18 was used to select features, and deconvolutional layers were used to upscale and increase the resolution of the images.
<img src="https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/Fig.1_pre-trained_model.png?raw=true">

## Training Model [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1AFxY4jd1_G22KS3teCVzE-RLKcHecU7w?usp=sharing) 
Based on the pre-trained model, additional training was conducted using cell images captured by microscopes.
<img src="https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/Fig.2_Training_model.png?raw=true">

## Citation
- Dataset: [MIT Places](http://places.csail.mit.edu/)
- Reference Code: [Automatic-Image-Colorization (GitHub)](https://github.com/lukemelas/Automatic-Image-Colorization/)
