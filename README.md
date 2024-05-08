# MS-lesion-detection
Detection of lesions in multiple sclerosis using nnUNet

This work focuses on the detection of multiple sclerosis lesions through the nnUNet architecture using MRI. In this work, we will demonstrate how medical segmentation can be performed.
In this case it will be used basal images of T1w and Flair for the training and a binarized lesion mask.
Adapt all the working directories.

## Requirements
1. Google Account.
2. At least 10 Gb of free disk.
3. Google colab Pro with minimum 100 instances.
4. Visualization tool for volumetric data. I used MITK Workbench.

## Notes
This work was created by Gerard Ramos Gambús, Data Science Master's student in the Universitat Oberta de Catalunya, headed by Eloy Martínez de las Heras.

To begin with, we have a dataset of 1160 NIFTI images which are divided into different instances of T1w and FLAIR. Additionally, there are lesion masks and two differentiations of lesions: SEL and noSEL, in case segmentation and classification of SELs are desired. In this case, segmentation of multiple sclerosis lesions is performed.
All these files must be in the correct format before the code can be used.
