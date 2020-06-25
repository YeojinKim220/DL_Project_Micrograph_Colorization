# Deep Learning Project - Micrograph Colorization
**CNN을 이용한 전자현미경 이미지 채색**


----------------------------

## Table of Contents
- [Introduction](#introduction)
- [Example Images](#example-images)
- [Datasets](#datasets)
- [Pre-training Model](#pretraining-model)
- [Training Model](#training-model)
- [Citation](#citation)

----------------------------

## Introduction

뉴스나 신문에서 쉽게 찾아 볼 수 있는 코로나 바이러스의 전자현미경 사진들이 모두 원래는 흑백사진이라는 것을 알고 계신가요? 전자빔을 이용하는 특성상 전자현미경 사진은 흑백일 수밖에 없기 때문에, 흑백사진을 포토샵으로 이용해서 보기 편하게 채색을 하는 것입니다. 
포토샵을 이용하지 않고 전자현미경 사진을 딥러닝을 이용해서 컬러링 하는 프로젝트를 진행해 보았습니다. 


1. Pre-training CNN Model with MIT Places Images : 40000여개의 풍경 사진을 이용한 pre-training | [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1J_kLfx5d0VWTJZDehBXU9_VAcVRoAPFV#scrollTo=rRoQxRmuWqnG) 
1. Training CNN Model with Micrograph Image : 현미경 image를 이용한 training | [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1AFxY4jd1_G22KS3teCVzE-RLKcHecU7w#scrollTo=Zfp5Ce54Hbyf) : 
1. Micrograph Colorization : image URL을 입력하면 colorization 하는 CNN model | [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1H1A78ZW90MhNQgFCAFcW3S8RR1FpQanp#scrollTo=MPNK98Emmf9j) : 

## Datasets
- Pre-training : [MIT Places](http://places.csail.mit.edu/) - 41,000개의 풍경이나 건물 이미지
- Training : [Micrograph Image DataSets (color)](https://drive.google.com/file/d/1Jd9RmimqICSzJDTbpk94BZQmdDKfoskh/view?usp=sharing) - Google Image Crawling 이용해서 구축한 4,845개의 현미경 세포 이미지

## Example Images
![example_image_1](https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/example_image_1.png?raw=true)

## Pretraining Model
Data Crawling을 이용해서 얻은 현미경 사진 데이터의 규모가 작기 때문에 이를 보완하기 위해서 transfer learning을 적용했다. 데이터가 풍부한 풍경 사진 데이터를 이용해서 colorization 모델을 pre-training 하는 과정입니다.

[MIT Places](http://places.csail.mit.edu/)데이터 중, 41,000개의 풍경이나 건물 이미지를 이용해서 pre-training을 진행했습니다. 

CNN(convolutional neural network)을 사용하였고 ResNet-18을 이용해서 feature를 선별하고, deconvolutional layers를 이용해서 upscale하여 resolution을 높이는 모델을 사용했습니다.
[<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/1J_kLfx5d0VWTJZDehBXU9_VAcVRoAPFV#scrollTo=rRoQxRmuWqnG)
<img src="https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/Fig.1_pre-trained_model.png?raw=true">

## Training Model
Pre-training model를 기반으로 현미경으로 촬영한 세포 이미지 데이터로 model을 추가로 학습시켰습니다. 
[<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">] (https://colab.research.google.com/drive/1AFxY4jd1_G22KS3teCVzE-RLKcHecU7w#scrollTo=Zfp5Ce54Hbyf)
<img src="https://github.com/YeojinKim220/DL_Project_Micrograph_Colorization/blob/master/Fig.2_Training_model.png?raw=true">

## Citation
- Dataset : [MIT Places](http://places.csail.mit.edu/)
- Reference Code : [Automatic-Image-Colorization (github)](https://github.com/lukemelas/Automatic-Image-Colorization/)

