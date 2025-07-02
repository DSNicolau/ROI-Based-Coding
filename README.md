# ROI-Based Coding for Mitochondria Detection in Electron Microscopy Images

This repository contains code and data associated with a study on enhancing the detection of mitochondria in compressed electron microscopy (EM) images using region-of-interest (ROI)-based coding and YOLOv8 detection models.

**Note:** This repository accompanies ongoing research work and is provided for reproducibility and transparency. Results and code may be subject to updates following peer review or publication.

## Overview

Advancements in imaging technologies have led to significant increases in the volume of biomedical data. Efficient compression of such data is crucial, especially when paired with downstream computer vision tasks such as object detection.

This work explores two key strategies to enhance mitochondria detection in compressed EM images:

**Model Fine-Tuning:** YOLOv8 models are retrained on compressed data to increase robustness to compression artifacts. The corresponding model checkpoints are provided in [checkpoints/](./checkpoints/)

**ROI-Based Coding:** Modified implementations of the HEVC (H.265) and VVC (H.266) codecs are used to assign higher quality to mitochondria regions while applying more aggressive compression to background areas. These modifications enable quality assignment at the coding unit (CU) level, allowing for separate quality control of foreground and background regions down to 8×8 blocks in HEVC and 4×4 blocks in VVC. Please refer to each submodule’s README for build and usage instructions.


## Datasets
Experiments were conducted on two publicly available EM datasets: Lucchi++ and Kasthuri++.
For more information about the datasets and to download them, please refer to [https://casser.io/connectomics/](https://casser.io/connectomics/). Refined bounding box annotations for mitochondria are provided in [detection_annotations/](./detection_annotations/) organized by dataset and split into training, validation, and test subsets.
