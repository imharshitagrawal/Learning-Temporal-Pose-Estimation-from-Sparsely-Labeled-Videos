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


