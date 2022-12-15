# Masked-Face-Recognition

USED: 
->Deep Learning including classifications
->SSD object detection
->FaceNet
->Inception Resnet

Worked on data preparation of people with no masks and masks, data cleaning and data augmentation.
Built a model to recognise the masked face person using the facial features. 
Can work in real time to detect and recognise multiple masked faces


Procedure:
1) Pre-Processing Data: Firstly we randomly selected 2000 image folders from around 10000 folders and then we cropped their faces using SSD face detection(or MTCNN). Then we cleaned the images using following steps-
  A) Selected images one by one in the same class as the target image. Others were regarded as reference images.
  B) Calculated average distances between target and reference images.
  C) Used the threshold value of 0.7.
  D) Removed the images whose avg. distance was greater than threshold.
  E) Then we created a dataset with facial masks. We used a set of different face masks with a transparent background. Then we detected the mouth of the person using          Dlib and created their masked images and then stored them in a different directory.
  
2) Creating Classification Model: We created FaceNet model by modifying the simple classification model which uses simple Resnet to Inception ResNet v1.

3) Training: We trained our model using both our datasets i.e. with and without masks images and saved our state in a log file(pb file) that was used in further evaluations. We used 50 epochs for training our model.
