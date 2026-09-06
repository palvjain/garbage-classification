# Garbage Classification

Sorts images of trash into 6 types: cardboard, glass, metal, paper, plastic, trash. Built two versions to see which works better — a CNN from scratch, and one using a pretrained MobileNetV2.

## How it works

Images are resized to 150x150. Since the dataset is small, I added augmentation (rotation, flipping, zooming, shifting) so the model sees more variety during training.

- First model: built from scratch, 3 conv layers with dropout in between, then dense layers ending in a softmax for the 6 classes.
- Second model: MobileNetV2 (pretrained, frozen) as the base, with a small custom head added on top.

Both trained for 10 epochs.

## Results

| Model | Val Accuracy |
|---|---|
| From scratch | ~51% |
| MobileNetV2 | ~84% |


## Dataset

[Garbage Classification dataset](https://www.kaggle.com/datasets/asdasdasasdas/garbage-classification) on Kaggle, ~2500 images across the 6 categories.


## Running it

Needs TensorFlow, NumPy, Pandas, Matplotlib.
