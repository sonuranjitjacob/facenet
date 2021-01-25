# Face Recognition using Tensorflow - Windows version

This is a repo forked from http://travis-ci.org/davidsandberg/facenet.  
I have modified the python commands for the Tensorflow implementation to be compatible with Windows. You can see the changes by comparing my repo with the original repo.   
Tensorflow version used: 1.13.0  
Libraries Required: scipy matplotlib scikit-learn  
## Version Used
| Version Date     | Update |
|----------|--------|
| 2018-04-10 | Added new models trained on Casia-WebFace and VGGFace2 (see below). Note that the models uses fixed image standardization (see [wiki]

## Pre-trained models
I have used the pre-trained model below in my code - you will need to create your own folder 'models' and change the path accordingly in data/test.py. 
| Model name      | LFW accuracy | Training dataset | Architecture |
|-----------------|--------------|------------------|-------------|
| [20180402-114759](https://drive.google.com/open?id=1EXPBSXwTaqrSC0OhUdXNmKSh9qJUQ55-) | 0.9965        | VGGFace2      | [Inception ResNet v1](https://github.com/davidsandberg/facenet/blob/master/src/models/inception_resnet_v1.py) |

## Commands

To align the datasets using MTCNN:
```
python C:/Users/sonur/Downloads/Bio/facenet-master/src/align/align_dataset_mtcnn.py "C:/Users/sonur/Downloads/Bio/Dataset/Chang/Blur" "C:/Users/sonur/Downloads/Bio/Dataset/Changprocessed/BlurProcessed" --image_size 160 --margin 32 --random_order --gpu_memory_fraction 0.25
```
where  
"C:/Users/sonur/Downloads/Bio/Dataset/lfw/raw – path to images  
C:/Users/sonur/Downloads/Bio/Dataset/processed – path where you want aligned images to be stored

To evaluate the results on the LFW dataset:
```
python C:/Users/sonur/Downloads/Bio/facenet-master/src/validate_on_lfw.py "C:/Users/sonur/Downloads/Bio/Dataset/Changprocessed/BlurProcessed" "C:/Users/sonur/Downloads/Bio/facenet-master/models/20180402-114759" --distance_metric 1 --use_flipped_images --subtract_mean --use_fixed_image_standardization
```
where    
"C:/Users/sonur/Downloads/Bio/facenet-master/models/20180402-114759" is the path to the pre-trained model

## Performance
To run the test use the description found on the page [Validate on LFW](https://github.com/davidsandberg/facenet/wiki/Validate-on-lfw). Note that the input images to the model need to be standardized using fixed image standardization (use the option `--use_fixed_image_standardization` when running e.g. `validate_on_lfw.py`).
