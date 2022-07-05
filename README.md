# Video-Classification - UCF101

## Problem Space
Video captures a cross-secton of our society. Major advances in analyzing and understanding video have the potental to touch all aspects of life from learning and communicaton to entertainment and play. A subset of the video analysis problem is human acton recogniton which involves analysis of realistic acton videos.<br />
Example: Skiing, Juggling Balls, Horse Riding

Action recogniton on large categories of unconstrained videos taken from the web is a very challenging problem due to challenges arising from camera motion, clutered background, bad illuminaton conditons, and poor quality of web videos cause the majority of the state-of-the-art approaches to fail.
We plan on tackling these challenges by performing video analysis to assign video-level labels.

## Dataset

We are using the Action Recogniton dataset- UCF-101 to identify human actions in videos. <br />
Total Number of samples: 13,320 video clips <br />
Train Data Size: 9537 video clips <br />
Test Data Size: 3783 video clips <br /> 
Number of Class Labels: 101 action categories <br />
Frame Rate (chosen): 5 FPS

## Approach

We are using 3 different CNN models to perform multi-class classification on the videos. <br />
- Conversion of Videos to Images: Using OpenCV at 5 frames/second <br />
- Creation of Feature Vectors for Images: Using pre-trained models ResNet-18, VGG-11 and AlexNet <br />
- Normalization of Feature Vectors: For pixel values between 0 and 1 <br />
- Multi-Class Classification: Fully Connected Layers with a last softmax layer to perform multi-class classification of images extracted <br />

**Model 1:** This model consists of an initial ResNet-18 model followed by a 5 layer fully connected model. <br />

<img width="450" alt="ResNet_A" src="https://user-images.githubusercontent.com/29837264/177226693-541937f6-6f9e-450c-963f-f0b8d728dc84.png">

**Model 2:** This model consists of an initial VGG-11 model followed by a 5 layer fully connected model.

<img width="450" alt="VGG_A" src="https://user-images.githubusercontent.com/29837264/177226687-39bed5d4-192d-485d-aa0a-f3756d290609.png">

**Model 3:** This model consists of an initial AlexNet model followed by a 5 layer fully connected model.

<img width="450" alt="AlexNet_A" src="https://user-images.githubusercontent.com/29837264/177226702-617c7b74-11b2-481b-ba9f-50ca36116d10.png">


## Results

The predicted labels are compared against the actual label to evaluate the performance of the model using the accuracy score. 

| No. | Approach | Test Accuracy |
|-----|----------|---------------|
| Exp. 1 | ResNet-18 + MLP | 69.78% | 
| Exp. 2 | VGG-11 + MLP    | 67.22% |
| Exp. 3 | AlexNet + MLP  |  54.4% |

