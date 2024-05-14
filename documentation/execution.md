## How to train nnUNet

To train nnUNet, you need to prepare the environment variables and the required JSON file first.

**Environment variables:**
```python
import os
os.environ['nnUNet_raw'] = "/content/..."
os.environ['nnUNet_preprocessed'] =  "/content/..."
os.environ['nnUNet_results'] = "/content/..."
```
Next, create the JSON file. You can use the `generate_dataset_json` method provided by nnUNet.

Before training the model, it's essential to verify that the dataset and its structure are correct. You can do this by running:
```!nnUNetv2_plan_and_preprocess -d 101 --verify_dataset_integrity```

Finally, execute the training:
```
!nnUNetv2_train Dataset101 3d_fullres 0 -tr nnUNetTrainer_10epochs --npz
!nnUNetv2_train Dataset101 3d_fullres 1 -tr nnUNetTrainer_10epochs --npz
!nnUNetv2_train Dataset101 3d_fullres 2 -tr nnUNetTrainer_10epochs --npz
!nnUNetv2_train Dataset101 3d_fullres 3 -tr nnUNetTrainer_10epochs --npz
!nnUNetv2_train Dataset101 3d_fullres 4 -tr nnUNetTrainer_10epochs --npz
```

These commands will train the nnUNet model on the specified dataset. Make sure to replace `/content/...` with the correct paths and dataset names as per your setup.

Now you can run the [inference](inference.md).
