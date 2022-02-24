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

![image](https://user-images.githubusercontent.com/29517840/155578431-8df8e5da-84bc-425b-a2bb-bd20928eeee5.png)

![image](https://user-images.githubusercontent.com/29517840/155578536-2906a852-bd17-4dad-be8c-7b354650913c.png)


