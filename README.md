# Segmentation in Unstructured Environments for Robotic Navigation 🤖🌿

This project explores deep learning techniques for semantic segmentation in unstructured outdoor environments to improve autonomous robotic navigation. We evaluate CNN-based architectures and optimisation strategies on the RUGD (Robot Unstructured Ground Driving) dataset, a challenging benchmark containing diverse terrains and severe class imbalances.

---

## ⚠️ Notebook Execution Note

> **Please note:** The notebook included in this repo is not designed to be executed end-to-end.  
> It was prepared for presentation purposes and contains commented code and inserted result images from different team members' Kaggle notebooks.

---

## Project Overview

### Problem Statement

> Improve semantic segmentation performance on the RUGD dataset to help robots navigate and understand unstructured environments.

We tested three baseline models and applied a variety of optimisation techniques to enhance segmentation accuracy, particularly on underrepresented terrain classes.

---

### Dataset

- RUGD Dataset: 7,456 annotated frames from video of a robot traversing off-road environments
- Contains 25 semantic classes (e.g., mulch, log, rockbed, water, grass)
- Severe class imbalance and challenging visual conditions (lighting, motion blur, etc.)

---

### Models & Methods

#### Architectures
- U-Net with ResNet50 backbone
- PSPNet with Dilated Convolutions
- PSPNet + Deep Supervision

#### Optimisation Techniques
- Hyperparameter Tuning
- ASPP Modules
- Class-Aware Loss Weighting
- Custom Data Augmentation:
  - Cropping & Resizing
  - CutMix
  - StickerMix (Novel method)

---

## Key Contribution: StickerMix

> **StickerMix** is a novel augmentation method that improves rare-class representation by pasting "stickers" (cropped regions) of underrepresented classes into training images. It demonstrated improvements in class-specific performance and showed potential for future development.

---

## Summary of Results

- Best baseline: U-Net + ResNet50
- Some optimisation strategies (like ASPP & loss weighting) improved results individually
- Combined methods did not outperform baseline, highlighting challenges in strategy compatibility
- StickerMix improved underrepresented class performance but not overall model performance

---

## My Contributions

- Full exploratory data analysis and data preprocessing pipeline
- Implemented the U-Net + ResNet50 baseline
- Designed and implemented StickerMix
- Assembled and documented the final presentation notebook

---

## Files in This Repository

```text
├── final_showcase.ipynb    # Read-only presentation notebook with code/comments/results
├── Project Report.pdf      # Final written team report
└── README.md               # Project documentation and context
```

## Authors
This project was completed as part of COMP9444 – Neural Networks and Deep Learning @ UNSW. The team consisted of:
- Jonas Macken
- Man Ching Chan
- Zirui Wang
- Dimas Putra Anugerah
- Aryan Wadhawan

## Future Work
Some ideas for future work include:
- Automate class balancing in StickerMix using per-class pixel stats
- Explore GAN-based rare-class augmentation
- Train at full resolution with more GPU time
