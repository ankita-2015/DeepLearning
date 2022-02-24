## A Deep Learning project on Multi-class Semantic Segmentation on [Indian Driving Dataset](https://idd.insaan.iiit.ac.in/dataset/details/)

## About Dataset
I have used dataset which is available at [kaggle](https://www.kaggle.com/abhishekprajapat/idd-20k)

Dataset provides image resolution of (**width**:1920, **height**:1080):
  1. Training Images: 5966
  2. Validation Images: 1016

The label image consists of 26 classes.

For this project, i have customized the number of classes:
1. There are 2 main classes: 

      - **Road** (Drivable)
      - **Moving objects** (Living things and Vehicles category as per this [offical dataset](https://idd.insaan.iiit.ac.in/dataset/details/))
      - **Background** (Rest of the categories as background which includes Non Drivable, Road Side Objects, Sky, Far Objects)

After mapping it to 3 categories, label image looks like: 

![image](https://user-images.githubusercontent.com/29517840/155579163-ac7d5251-1536-423a-8a7b-5140c9c9e503.png)

Script to customize number of classes for IDD dataset is available at [/Scripts/DatasetPreparation/prepare_IDD_dataset.ipynb](https://github.com/ankita-2015/DeepLearning/blob/main/Semantic%20Segmentation/Obstacle%20Segmentation/Scripts/DatasetPreparation/prepare_IDD_dataset.ipynb)
