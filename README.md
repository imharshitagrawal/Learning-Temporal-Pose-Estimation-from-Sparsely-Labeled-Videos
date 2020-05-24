# Learning-Temporal-Pose-Estimation-from-Sparsely-Labeled-Videos
This project is an implementation of the 2019 research paper "Learning Temporal Pose Estimation from Sparsely Labeled Videos(NeurIPS 2019)"

### Introduction
This is a tensorflow implementation of the research paper [***Learning Temporal Pose Estimation from Sparsely Labeled Videos***](https://arxiv.org/abs/1906.04016) by Gedas Bertasius, Christoph Feichtenhofer, Du Tran, Jianbo Shi, Lorenzo Torresani. In this work, the authors introduce a framework that reduces the need for densely labeled video data, while producing pose detection performance. Modern approaches for multi-person pose estimation in video require large amounts of dense annotations. However, labeling every frame in a video is costly and labor intensive. To reduce the need for dense annotations, they propose a PoseWarper network that leverages training videos with sparse annotations (every k frames) to learn to perform dense temporal pose propagation and estimation. Given a pair of video frames—a labeled Frame A and an unlabeled Frame B—we train our model to predict human pose in Frame A using the features from Frame B by means of deformable convolutions to implicitly learn the pose warping between A and B.  

![mod2](https://user-images.githubusercontent.com/45999827/82759724-c62f3480-9e0c-11ea-97b0-19627f172f6c.JPG)

### Datasets used
The dataset used in this project is [***Posetrack 2018***](https://posetrack.net/users/download.php). Overall data set contains 550 video sequences which includes 66,374 frames. The length of the training videos ranges between 41–151 frames and they densely annotated 30 frames from the center of the video. There are 17 key points annotated for each person. 

An example of a labeled frame with bounding boxes and keypoints applied to each person -

![1_D7hq1ULqzLedjkhwH1NwPg](https://user-images.githubusercontent.com/45999827/82748359-ca346580-9dbe-11ea-9162-6543508b1e01.jpeg)

However due to limited resources, we have not used the entire posetrack 2018 dataset but only 52 training videos to train our model. The  dataset used in this project can be found [here](https://drive.google.com/drive/folders/1CFvc1NeO3Un9aE1tf5GL4TAaifrlR2nv?usp=sharing)

### Models Used
This project uses Residual Networks, state-of-thE-art High Resolution Network HRNET-W48, simple convolutional layers and deformable convolutional layers for pose warping. The complete model description is as follows:-

![mod](https://user-images.githubusercontent.com/45999827/82759634-499c5600-9e0c-11ea-9e0d-60a89f078036.JPG)

### Software Environments
This project has been completed in Google Colab environment. 

The following frameworks and libraries have been used:
1. Tensorflow and Tensorlayer
2. PIL
3. Pycocotools
4. skimage
5. math
6. random
7. json
8. time
9. Numpy, Matplotlib

### Results

Due to only 10% of data available and running for 5 epochs, we achieved about only 30% accuracy on our training data.

![mod4](https://user-images.githubusercontent.com/45999827/82760199-9cc3d800-9e0f-11ea-8109-618eb9dcaff8.JPG)

For an input cropped image to the network 
![3 (1)](https://user-images.githubusercontent.com/45999827/82760466-48215c80-9e11-11ea-8b68-cebeb38aef0a.jpg)

we got the output
![1 (1)](https://user-images.githubusercontent.com/45999827/82760450-3e97f480-9e11-11ea-9a34-70905de4ebf7.jpg)
The ground truth corresponding to the input was :
![2 (1)](https://user-images.githubusercontent.com/45999827/82760462-42c41200-9e11-11ea-9444-cff09fa0a8b9.jpg)


