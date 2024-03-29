## Scripts for TensorFlow Lite Object Detection
These scripts are used in the [TFLite Training Colab] to help with various steps of training a custom model. They can also be used as standalone tools.

### Calculate model mAP - (calculate_map_analysis.py)
Calculate your TFLite detection model's mAP score! I'll share instructions on how to use this outside the Colab notebook later. 

This tool uses the main.py script from [Cartucho's excellent repository](https://github.com/Cartucho/mAP), which takes in ground truth data and detection results to calculate average precision at a certain IoU threshold. The calculate_map_analysis.py script performs the mAP calculation at multiple IoU thresholds to determine the COCO metric for average mAP @ 0.5:0.95.

### Split images into train, test, and validation sets - (train_val_test.py)
This script takes a folder full of images and randomly splits them between train, test, and validation folders. It does an 80%/10%/10% split by default, but this can be modified by changing the `train_percent`, `test_percent`, and `val_percent` variables in the code.

### Create CSV annotation file - (create_csv.py)
This script creates a single CSV data file from a set of Pascal VOC annotation files.

### Create TFRecord file - (create_tfrecord.py)
This script creates TFRecord files from a CSV annotation data file and a folder of images. TFRecords are the [data format required](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/preparing_inputs.md) by the TensorFlow Object Detection API for training.

