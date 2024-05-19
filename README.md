# MS-lesion-detection
Detection of lesions in multiple sclerosis using nnUNet

This work focuses on the detection of multiple sclerosis lesions through the nnUNet architecture using MRI. In this work, we will demonstrate how medical segmentation can be performed.
In this case it will be used basal images of T1w and Flair for the training and a binarized lesion mask.

## Requirements
1. Google Account.
2. At least 10 Gb of free disk.
3. Google colab Pro with minimum 100 instances of GPU.
4. Visualization tool for volumetric data. I used [MITK Workbench](https://docs.mitk.org/nightly/MITKWorkbenchManualPage.html).

## Notes
This work was created by Gerard Ramos Gambús, Data Science Master's student in the Universitat Oberta de Catalunya, headed by Eloy Martínez de las Heras.

## Data
To begin with, we have a dataset of 1160 NIFTI images which are divided into different instances of T1w and FLAIR. These images correspond to 129 different people diagnosed with MS. Additionally, we also have our Gold Standard, the lesion masks, which are files where the lesions are identified. Masks files are labeled with 1: lesion detected, 0: no lesion detected.
All these files must be in the correct format before the code can be used.

It is needed to have a specific folder structure with all MRI separated:

`nnUNet_raw`:

    ```
    nnUNet_raw/Dataset101
    ├── dataset.json
    ├── imagesTr
    │   ├── ...
    ├── imagesTs
    │   ├── ...
    └── labelsTr
        ├── ...
    nnUNet_raw/Dataset102
    ├── dataset.json    
    ├── imagesTr    
    │   ├── ...    
    ├── imagesTs    
    │   ├── ...    
    └── labelsTr    
        ├── ...        
    ```
`nnUNet_preprocessed`: This is the folder where the preprocessed data will be saved. The data will also be read from this folder during training.

`nnUNet_results`: This specifies where nnU-Net will save the model weights.


## Preprocessing
MRI properties:
- Dimension: (208, 256, 256)
- Voxel size: (0.86, 0.859375, 0.859375)
- Intensity value range: 0.0 - 271.0

Mask label properties:
- Dimension: (208, 256, 256)
- Voxel size: (0.86, 0.859375, 0.859375)
- Intensity value range: 0.0 - 1.0

Originally, the MRI came with the skull, but a more precise result can be obtained by removing it using [HD-Bet](https://github.com/MIC-DKFZ/HD-BET).

Next steps:
- [Execution](documentation/execution.md): Now it is time to train the nnU-Net with all our data.
- [Inference](documentation/inference.md): Here is where predictions are made.

