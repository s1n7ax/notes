# Binary Classification with Food 101 Dataset - Visualizing Data

## Summary

- Download data and visualize data

## Content

### Download data and visualize data

```python
# get data
import zipfile

!wget https://storage.googleapis.com/ztm_tf_course/food_vision/pizza_steak.zip

# extract data
zip_ref = zipfile.ZipFile("pizza_steak.zip")
zip_ref.extractall()
zip_ref.close()

# show directory structure
!sudo apt install tree
!tree -d pizza_steak
"""
pizza_steak
├── test
│   ├── pizza
│   └── steak
└── train
    ├── pizza
    └── steak
"""

# data count
import os

print(len(os.listdir("pizza_steak/train/pizza")), len(os.listdir("pizza_steak/train/steak")))
print(len(os.listdir("pizza_steak/test/pizza")), len(os.listdir("pizza_steak/test/steak")))
"""
750 750
250 250
"""

# view random images from the data
import random
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

def view_random_image(target_dir, target_class):
    images_path = target_dir + "/" + target_class
    rand_img = random.sample(os.listdir(images_path), 1)
    image_path = images_path + '/' + rand_img[0]

    image = mpimg.imread(image_path)
    plt.imshow(image)
    plt.title(target_class + f" [shape: {image.shape}]")
    plt.axis('off')


view_random_image('pizza_steak/train', 'pizza')
```
