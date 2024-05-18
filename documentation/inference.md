## Run inference

``nnUNetv2_find_best_configuration`` will print a string to the terminal with the inference commands you need to use. The easiest way to run inference is to simply use these commands.
If you wish to manually specify the configuration(s) used for inference, use the following commands:

### Run prediction
``!nnUNetv2_predict -d Dataset101_SEL -i /content/nnUNet_SEL/nnUNet_raw/Dataset101_SEL/imagesTs -o /content/nnUNet_SEL/nnUNet_results/Dataset101_SEL/inference -f  0 1 2 3 4 -tr nnUNetTrainer_10epochs -c 3d_fullres -p nnUNetPlans``

### Apply postprocessing
``nnUNetv2_apply_postprocessing -i FOLDER_WITH_PREDICTIONS -o OUTPUT_FOLDER --pp_pkl_file POSTPROCESSING_FILE -plans_json PLANS_FILE -dataset_json DATASET_JSON_FILE``

When using ``nnUNetv2_find_best_configuration`` (or its generated inference_instructions.txt file), it will guide you to locate the postprocessing file. 
If you can't find it there, simply look for it in your results folder (typically named postprocessing.pkl). 
If your source folder comes from an ensemble, you'll also need to specify a ``-plans_json`` file and a ``-dataset_json`` file to be used 
(for single configuration predictions, these are automatically copied from the respective training). You can select these files from any ensemble member.
