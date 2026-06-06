# BookSpineDataset

This repository provides the dataset used in our paper for book spine localization and instance-level text extraction in library shelf images.

The dataset is released mainly for research reproducibility.
## Download

Due to the file size of the image data, the complete dataset is not stored directly in this repository.

The full dataset, including images, labels, split files, and SpineText-40 annotations, is provided as a compressed archive:

```text
spine_datasets.zip
```

Please download the complete dataset from the Releases page of this repository.

After extraction, the dataset structure should be:

```text
spine_datasets/
├── images/
├── labels/
├── SpineText-40/
├── train.txt
├── val.txt
├── test.txt
├── dataset.yaml
├── README.md
└── LICENSE
```

## Dataset Description

The images were collected in the Lingang Campus Library of Shanghai Dianji University using a personal smartphone under indoor lighting conditions.

The dataset contains 1,505 bookshelf images. The images mainly include densely arranged book spines with elongated shapes, orientation variations, and occasional occlusion or truncation caused by viewpoint changes.

Each book spine is annotated using an oriented bounding box. The annotations follow the Ultralytics YOLO Oriented Bounding Boxes format.

## Dataset Structure

```text
spine_datasets/
├── images/
├── labels/
├── SpineText-40/
├── train.txt
├── val.txt
├── test.txt
├── dataset.yaml
├── README.md
└── LICENSE
```

## Detection Dataset

The `images/` folder contains all bookshelf images.

The `labels/` folder contains the corresponding oriented bounding box annotations. Each image has a label file with the same file name.

For example:

```text
images/000001.jpg
labels/000001.txt
```

Each line in a label file represents one book spine instance:

```text
<class_id> <x1> <y1> <x2> <y2> <x3> <y3> <x4> <y4>
```

where the eight coordinates represent the four vertices of the oriented bounding box. The only category is:

```text
0 book_spine
```

## Dataset Split

The dataset split is specified by the following files:

```text
train.txt
val.txt
test.txt
```

The split is:

| Split      | Number of Images |
| ---------- | ---------------: |
| Train      |              903 |
| Validation |              301 |
| Test       |              301 |
| Total      |            1,505 |

The images and labels are not stored in separate `train`, `val`, and `test` folders. Instead, the split files specify which images belong to each subset.

## SpineText-40

The `SpineText-40/` folder provides text annotations for evaluating instance-level book spine text extraction.

It contains 40 selected bookshelf images and manually annotated visible text for book spine instances. The annotated text includes book titles, author names, publisher information, call numbers, and other readable text on book spines.

Only visible text is annotated. Invisible, occluded, or truncated text is not manually completed.

## Usage

This dataset can be used for:

* oriented book spine detection
* book spine localization
* detection-guided OCR
* instance-level book spine text extraction
* smart library image analysis

## Notes

This dataset is provided for academic research and reproducibility purposes. Please do not use it for commercial purposes without permission.

If you use this dataset in your research, please cite the corresponding paper after it is published.

## Contact

Yanan Wu
School of Electronic Information
Shanghai Dianji University
