# Yolo Object Detection Tutorial

## Prerequisits

* jupyter notebook
* torch
* pandas
* mypy (optional)
* black (optional)

## Yolo V5

Thanks to **Joos Korstanje** for his [article](https://towardsdatascience.com/yolo-v5-object-detection-tutorial-2e607b9013ef).

Run `task yolov5:start` to open the jupyter notebook with the tutorial.

### Data structure

```bash
data
├── images
│   ├── train
│   └── valid
└── labels
    ├── train
    └── valid
```

*The images* have to be directly in the **image** folders. Training images in the `data/images/train` folder and validation images in the `data/images/valid` folder. The names of the images have to be simply unique names with a `.jpg` (or another format).

*The labels* have to be in the `data/labels/train/` or in the `data/labels/valid`. **The name of the labels file has to be the same name as the image**, but with `.txt`.

The bounding boxes have to be listed as **one bounding box per line**, with on that line:

* the **class number of the object** in the bounding box (always 0 if only one class)
* the standardized **center** pixel of the bounding box in terms of **width**
* the standardized **center** pixel of the bounding box in terms of **height**
* the standardized **width** of the **bounding box**
* the standardized **height** of the **bounding box**

**Standardization is done by dividing the number of pixels by the total number of pixels of the image**. So a bounding box on pixel (10, 20) with a width of 30x40 on a picture of size (100, 100) would be standardized to (0.1, 0.2, 0.3, 0.4).

> The number of lines of the label file is the number of bounding boxes in one image. The number of label files is the number of images.
