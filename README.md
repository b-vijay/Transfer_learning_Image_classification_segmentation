## Deep Learning for Fruit Classification & Segmentation
Developed deep learning models for identifying the fruit type in an image (classification) and isolating the fruit region at the pixel level (segmentation). These are essential in applications like automated fruit sorting, quality assessment and in precision agriculture. To achieve this, transfer learning using the ResNet-50 architecture will be used.

### Overview

- **Framework**: PyTorch
- **Models Used**:
  - **Classification**: Pretrained **ResNet-50** (ImageNet1K) with frozen backbone and custom FC head
  - **Segmentation**: Custom CNN using ResNet-50 encoder + upsampling decoder
- **Training Strategy**:
  - Random hyperparameter search (optimizers: Adam, AdamW, SGD; LRs: 1e-3 to 1e-4)
  - Data augmentation: Rotation, Crop, Flip, ColorJitter for robustness (classification only)
  - Losses: CrossEntropy (classification), BCEWithLogits (segmentation)
  - Evaluation metrics: Accuracy, F1, Dice Score, IoU

### Results

| Task           | Model       | Metric         | Value     |
|----------------|-------------|----------------|-----------|
| Classification | ResNet-50   | Accuracy       | 98.73% (no aug) |
| Classification | ResNet-50   | Accuracy       | 91.62% (with aug) |
| Segmentation   | ResNet-50   | Dice Score     | 0.6531    |
| Segmentation   | ResNet-50   | IoU (Jaccard)  | 0.9419    |
