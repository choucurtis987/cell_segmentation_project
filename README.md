# Cell Segmentation Project
- [Abstract](#abstract)
- [Main Script](/cell_segmentation.ipynb)
## Background
- This code was done during my Community College Internship (CCI) at Lawrence Berkeley National Lab (LBNL) as a prerequisite to my research. This code displays similar work done with similar processes and the same model. My code for the research done during the internship could not be shared as it contained confidential data.
- **This project is used to display work similar to the things I worked on during my internship at LBNL**
## Project Goals
- Semantic segmentation of nuclei to identify two classes: background and foreground (cells / nuclei)
- Utilize Connected Component Analysis (CCA) on the segmented binary image to count nuclei
## Technical Background
- Semantic segmentation is segmenation of an image where the goal is to link each pixel to a class label
- Fully Convolutional Networks (FCN) are a variation of traditional CNNs commonly used for tasks like semantic segmentation
- Intersection Over Union (IOU) is a common semantic segmentation metric similar to dice coefficient. IOU tells us how closely correlated the predicted segmented image is to the ground truth segmented image on scale from 0 to 1. An IOU above 0.5 is generally considered a "good" prediction or model.
- CCA is a technqiue that labels regions of an image. In our case, it labels the white pixel areas (nuclei / foreground) surrounded by blacks pixels (background) as a region. CCA then labels the entire image and simultaneously counts the regions. Thus, number of nuclei / cells in the image can be found.

## Abstract
The [project](/cell_segmentation.ipynb) follows the traditional machine learning process of training and testing. The goals of the project are to achieve semantic segmentation of the nuclei / cell images and use [CCA](#technical-background) on the segmented image to count the cells in the image.
- The figure below is displaying an example of the X train (input) and Y train (ground truth) used to train the [FCN](#technical-background) model for semantic segmentation. 
<img src="/imgs/xtrain_ytrain.png" width=500/>

- This figure below is a graph of some model metrics after training. Accuracy refers to the pixel accuracy of the semantic segmentation.
<img src="/imgs/model_metrics.png" width=400/>

After training, we are able to used the trained [FCN](#technical-background) model for predictions. The figure below displays model predictions of some training data to compare to the ground truth data. 
- Post processing in the form of a threshold=0.5 is used to make the predicted image resemble the ground truth data more. A threshold also converts the predicted image into a binary image which is also the type of image used for Y train. 
<img src="/imgs/X_train_Predict.png"/>

Below is an example of model predictions on unseen test data. Despite the nuclei / cells being barely visible in the test input, the model is still able to pick it up. (zoom into input to see the barely visible nuclei)

<img src="/imgs/X_test_Predict.png" height=200/>

After predictions, we are able to take the [IOU](#technical-background) of the model predictions and apply [CCA](#technical-background) to the predicted image to count the nuclei in the image thus concluding and achieving the goals of this project. 

<img src="/imgs/simple_metrics.png"/>

## Resources
- [Dataset Link](https://www.kaggle.com/c/data-science-bowl-2018/data)
- [DigitalSreeni](https://www.youtube.com/channel/UC34rW-HtPJulxr5wp2Xa04w) , good resource for helping me understand semantic segmentation along with other machine learning concepts. His code aided in helping me clean and organize the data in this project. 
