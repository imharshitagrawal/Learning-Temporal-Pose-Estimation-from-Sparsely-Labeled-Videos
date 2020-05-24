# Learning-Temporal-Pose-Estimation-from-Sparsely-Labeled-Videos
This project is an implementation of the 2019 research paper "Learning Temporal Pose Estimation from Sparsely Labeled Videos(NeurIPS 2019)"

### Introduction
This is a tensorflow implementation of the research paper [***Learning Temporal Pose Estimation from Sparsely Labeled Videos***](https://arxiv.org/abs/1906.04016) by Gedas Bertasius, Christoph Feichtenhofer, Du Tran, Jianbo Shi, Lorenzo Torresani. In this work, the authors introduce a framework that reduces the need for densely labeled video data, while producing pose detection performance. Modern approaches for multi-person pose estimation in video require large amounts of dense annotations. However, labeling every frame in a video is costly and labor intensive. To reduce the need for dense annotations, they propose a PoseWarper network that leverages training videos with sparse annotations (every k frames) to learn to perform dense temporal pose propagation and estimation. Given a pair of video frames—a labeled Frame A and an unlabeled Frame B—we train our model to predict human pose in Frame A using the features from Frame B by means of deformable convolutions to implicitly learn the pose warping between A and B.  

### Datasets used
The dataset used in this project is [***Posetrack 2018***](https://posetrack.net/users/download.php). Overall data set contains 550 video sequences which includes 66,374 frames.
