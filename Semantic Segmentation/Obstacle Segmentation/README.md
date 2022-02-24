## A Deep Learning project on Multi-class Semantic Segmentation on [Indian Driving Dataset](https://idd.insaan.iiit.ac.in/dataset/details/)

## About Dataset
I have used dataset which is available at [kaggle](https://www.kaggle.com/abhishekprajapat/idd-20k)

Dataset provides image resolution of (**width**:1920, **height**:1080):
  1. Training Images: 5966
  2. Validation Images: 1016
I have used Validation images as Test Set for evaluation purpose and For training i have splitted Training images to train(4950) and Val set(1016)
The label image consists of 26 classes.

For this project, i have customized the number of classes:
1. There are 2 main classes: 

      - **Road** (Drivable)
      - **Moving objects** (Living things and Vehicles category as per this [offical dataset](https://idd.insaan.iiit.ac.in/dataset/details/))
      - **Background** (Rest of the categories as background which includes Non Drivable, Road Side Objects, Sky, Far Objects)

After mapping it to 3 categories, label image looks like: 

![image](https://user-images.githubusercontent.com/29517840/155579163-ac7d5251-1536-423a-8a7b-5140c9c9e503.png)

Script to customize number of classes for IDD dataset is available at [Scripts/DatasetPreparation/prepare_IDD_dataset.ipynb](https://github.com/ankita-2015/DeepLearning/blob/main/Semantic%20Segmentation/Obstacle%20Segmentation/Scripts/DatasetPreparation/prepare_IDD_dataset.ipynb)

## Training 
 
 - For training i have resized images to 512 X 512
   
   ![image](https://user-images.githubusercontent.com/29517840/155583808-7cf985e4-6c9f-43a4-b434-287a3da4a068.png)

- I have trained various models on this dataset with different techniques. All training scripts are present in [Scripts/TrainingScripts/](https://github.com/ankita-2015/DeepLearning/tree/main/Semantic%20Segmentation/Obstacle%20Segmentation/Scripts/TrainingScripts)
  - Deeplabv3p with MobilenetV2 with pretrained [Cityscapes weights](https://github.com/bonlime/keras-deeplab-v3-plus/releases/download/1.2/deeplabv3_mobilenetv2_tf_dim_ordering_tf_kernels_cityscapes.h5)
  - Deeplabv3p with Xception with pretrained [Cityscapes weights](https://github.com/bonlime/keras-deeplab-v3-plus/releases/download/1.2/deeplabv3_xception_tf_dim_ordering_tf_kernels_cityscapes.h5) 
  - Unet with MobilenetV2 with pretained encoder
  - Unet with EfficientNetB0 with pretained encoder
  - Unet with EfficientNetB1 with pretained encoder
  - Unet with EfficientNetB6 with pretained encoder
  - Unet with PSPNet with pretained encoder
  - Unet with FPN with pretained encoder
  - Unet with LinkNet with pretained encoder
  - Deeplabv3p with MobilenetV2(alpha 1.0) - custom model with pretrained encoder
  - Deeplabv3p with MobilenetV2(alpha 0.35) - custom model with pretrained encoder and decoder upsampled by 2
  - Deeplabv3p with MobilenetV2(alpha 0.35) - custom model with pretrained encoder and decoder upsampled by 4
  - Deeplabv3p with MobilenetV2(alpha 0.35) - custom model with pretrained encoder and decoder upsampled by 4, applied DepthwiseSeparable Convolution in decoder 
  - Deeplabv3p with MobilenetV2(alpha 0.3) - custom model trained from scratch 

## Evaluation

I have Evaluated models results on datasets:
  - IDD validation set (NOT used in training)
  - Cityscapes test set - 500 images - [prepare cityscape dataset](https://github.com/ankita-2015/DeepLearning/blob/main/Semantic%20Segmentation/Obstacle%20Segmentation/Scripts/DatasetPreparation/prepare_Cityscape_dataset.ipynb)
  - BDD100k test set - 1000 images - [prepare_BDD100k dataset](https://github.com/ankita-2015/DeepLearning/blob/main/Semantic%20Segmentation/Obstacle%20Segmentation/Scripts/DatasetPreparation/prepare_BDD_dataset.ipynb)






