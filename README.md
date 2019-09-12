# COCO-Assistant<img src="rep_images/coco.png" height="40">

Helper for dealing with MS-COCO annotations. 

## Overview
The MS COCO annotation format along with the pycocotools library is quite popular among the computer vision community. Yet I for one found it difficult to play around with the annotations. Deleting a specific category, combining multiple mini datasets to generate a larger dataset, viewing distribution of classes in the annotation file are things I would like to do without writing a separate script for each. The COCO Assistant is designed (or being designed) to assist with this exact problem.

### Requirements
Your data directory should look as follows:

```
Example:
.
├── images
│   ├── train
│   ├── val
|   ├── test
|   
├── annotations
│   ├── train.json
│   ├── val.json
│   ├── test.json
|── coco_assistant.py
|── coco_stats.py
|── coco_visualiser.py

``` 

## What can CASS do?:

#### Merge datasets

The `combine` function allows you to merge  multiple datasets. Note however, that the individiual annotations needs to have different annotation ids so that they can be seamlessly merged. In the future, functionality will be added to check annotation ids automatically.

#### Remove_cat

Removes a specific category from an annotation file.

#### Generate annotation statistics

1. Generate countplot of instances per category that occur in the annotation files.
2. Generate pie-chart that shows distribution of objects according to their size (as specified in areaRng).

#### Visualise annotations

Couldn't pycocotools visualise annotations (via the [showAnns](https://github.com/cocodataset/cocoapi/blob/636becdc73d54283b3aac6d4ec363cffbb6f9b20/PythonAPI/pycocotools/coco.py#L233)) as well? Sure it could, but I required a way to view all the annotations of a particular dataset so here we are.


### In Progress: 
#### COCO to YOLO Converter

Converts COCO annotations to YOLO format (modified version of ultralytics's [original repo](https://github.com/ultralytics/COCO2YOLO))
