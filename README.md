# Flood-segmentation
This code is built to perform supervised semantic segmentation of drone images of flooded areas
using Convolutional Neural Network UNet architecture and classification of flooded or not
flooded images with Support Vector Machine. \
The code was originally written in Google Colab and using Pytorch and Segmentation Models 
found at https://github.com/qubvel/segmentation_models.pytorch.

## Dataset
The dataset used can be found at https://github.com/BinaLab/FloodNet-Supervised_v1.0 \
The segmentation labels are grouped into: 'building flooded', 'road flooded', and 'background'. \
One can modify the script to use any set of classes.

### Classification labels
Labels 'flooded' / 'not flooded' are assigned to each image based on amount of flooded pixels 
in the original mask.

## Methods
The code is made up of different sections:
### Data preprocessing
- Data import and trasformation for pretrained network
- Possibility to perform data augmentation
- Data inspection with statistical functions
### Segmentation Model
- Definition, training and evaluation, and testing of UNet model with possibility to freeze
  layers of pretrained model.
  - Validation is done with different micro and macro scores.

### Classification
- First way: segmented images are classified based on number of flooded pixels
- Second way: feature extraction from last layer of UNet to perform classification with SVM.
- Comparison of the two ways.
