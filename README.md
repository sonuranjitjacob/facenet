# Face Recognition using Tensorflow 

This is a repo forked from http://travis-ci.org/davidsandberg/facenet
I have modified the python commands for the Tensorflow implementation to be compatible with Windows.
## Version
| Date     | Update |
|----------|--------|
| 2018-04-10 | Added new models trained on Casia-WebFace and VGGFace2 (see below). Note that the models uses fixed image standardization (see [wiki]

## Pre-trained models
I have used the pre-trained model below in my code - you will need to create your own folder 'models' ancd change the path accordingly. 
| Model name      | LFW accuracy | Training dataset | Architecture |
|-----------------|--------------|------------------|-------------|
| [20180402-114759](https://drive.google.com/open?id=1EXPBSXwTaqrSC0OhUdXNmKSh9qJUQ55-) | 0.9965        | VGGFace2      | [Inception ResNet v1](https://github.com/davidsandberg/facenet/blob/master/src/models/inception_resnet_v1.py) |


## Performance
To run the test use the description found on the page [Validate on LFW](https://github.com/davidsandberg/facenet/wiki/Validate-on-lfw). Note that the input images to the model need to be standardized using fixed image standardization (use the option `--use_fixed_image_standardization` when running e.g. `validate_on_lfw.py`).
