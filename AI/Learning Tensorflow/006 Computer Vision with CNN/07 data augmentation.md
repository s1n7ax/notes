# Data Augmentation

## Summary

- what is data augmentation
- how to do data augmentation
- applying data augmentation
  - applying to pre-processing layers to the data set
  - applying to the model layers itself

## Content

### What is Data Augmentation

Data augmentation is a technique in machine learning used to reduce overfitting
when training a machine learning model, by training models on several
slightly-modified copies of existing data

### How to Do Data Augmentation

Data augmentation can be done as a part of the model itself.

**NOTE:** That data augmentation is only active when `Model.fit` for obvious
reasons. When calling `Model.evaluate` or `Model.predict`, augmentation layers
will be inactive

**NOTE:** Even though, the augmentation layers are inactive, layers such as
`Rescaling` & `Resizing` layers will be active.

```python
import tensorflow as tf
import matplotlib.pyplot as plt

data_augmentation = tf.keras.Sequential(
    [
        tf.keras.layers.Rescaling(1 / 255),
        tf.keras.layers.RandomRotation(0.2),
        tf.keras.layers.RandomFlip("horizontal_and_vertical"),
    ]
)

plt.figure(figsize=(10, 10))

for i in range(9):
    augmented_image = data_augmentation(tf.expand_dims(image, 0))
    ax = plt.subplot(3, 3, i + 1)
    plt.imshow(augmented_image[0])
    plt.axis("off")
```

![Data augmentation output image](../../../assets/2024-01-11-23-09-04.png)
