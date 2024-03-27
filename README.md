# feral-cat-segmentation-dataset-and-model
Images and labels for feral cat instance segmentation model, plus the model itself.

This repository was developoed by Paul M. Cashman (pc232@cornell.edu) under the
sponsorship of the Cornell Feline Health Center in December 2023.

The repo is structured as follows:

Folder '200-epochs-'
    Folder 'weights'
        Contains the best model parameters (best.pt) and the last epoch's
            model parameters (last.pt).  I recommend using best.pt for
            inference.
    Files with results of the training runs.  See the YOLO v8 documentation
        for training (https://docs.ultralytics.com/modes/train/) to interpret
        those files.  I also recommend the YouTuve video at https://www.youtube.com/watch?v=ytlhMAF6ok0
        which describes in good detail how to train a YOLO v8 custom model.


Folder 'feral-cat-segmentation.v1i.yolov8'
    README files for dataset and roboflow.  The latter describes the augmentations
        that were applied to the original images to create this dataset.
    data.yaml describes where the train, test, and validation images and labels
        are with respect to the current directory.  If you want to retrain the 
        YOLO v8 model with another version of this dataset, I recommend uploading
        it to Colab or some other notebook platform that runs in the cloud and 
        gives access to GPUs.  You may have to edit data.yaml to ensure that it
        points to the right folders in your environment.  See the YOLO v8 training
        documentation.
    'train', 'test', 'valid' folders
        These contain the images and labels for training, testing, and validation.
        'test' and 'valid' contain 'images' and 'labels' folders.  The 'train'
        dataset includes 2054 images and an equal number of labels.  GitHub allows
        a maximum of 1000 files in a folder, so I broke both the subfolders into 5
        folders named 'images_1st_500', 'labels_1st_500', and so on.  When you train 
        a model, you should collect all the images into a single folder named 'images"
        (and the same for the labels folders).  Breaking them up into 500-item 
        subfolders is ajust an accommodation for GitHub.
