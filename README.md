# Object_Detection_In_Hazy_Condition

A repository for  [5th UG2+ challenge (CVPR 2022) Track 1.1 - Object Detection in the Hazy Condition] (https://codalab.lisn.upsaclay.fr/competitions/1235#results) using Deep Learning.

Following techniques were applied:
1. Generic Model-Agnostic Convolutional Neural Network(GMAN) is tested for haze removal.It is a convolutional neural network that employs the encoder-decoder network for denoising image. Model is trained from the scratch.
2. Dark Channel Prior is used for dehazing images. Most local patches in haze-free outdoor images contain some pixels which have very low intensities in at least one color channel. Using this prior with the haze imaging model, the thickness of the haze is estimated and a high quality haze-free image is recovered.
3. Pretrained Faster RCNN is used for vehicle detection in dehazed images.Faster R-CNN consists of two modules - a deep fully convolutional network that proposes regions, and the second module is the Fast R-CNN detector that uses the proposed regions.
4. Custom Object Detection using Pretrained Faster RCNN: Transfer learning is used to train our own dataset using learned features of the state-of-the-art pre-trained faster RCNN with the ResNet50 FPN backbone

Results  
Image Dehazing using GMAN, followed by vehicle detection using pretrained faster RCNN model : mAP 5.6


Image Dehazing using Dark Channel Prior, followed by vehicle detection using pretrained faster RCNN model (Colab Notebook Link) : mAP 14.96

Image Dehazing using Dark Channel Prior, followed by vehicle detection using  custom object detection on pretrained faster RCNN model : mAP 2.14 

