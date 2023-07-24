# Car Classifier: SUV or Supercar

This repository contains a machine learning project that classifies images of cars as either an SUV or a supercar.

## Overview

The project uses a convolutional neural network (CNN) to classify images of cars. The model is trained on a dataset of labeled car images and can accurately classify new images as either an SUV or a supercar.

## Data

The data was downloaded using google search using the search terms

- suv
- supercar

The images were downloaded using [Download All Images](https://chrome.google.com/webstore/detail/download-all-images/ifipmflagepipjokmbdecpmjbibjnakm)

## Data Preprocessing

The Data was First Augmented using Albumentations Pipeline.

The below filters were applied to Images to augment them:
- Horizontal Flip
- Random Brightness Contrast
- Random Rotate 90
- Flip
- RGB Shift
- Hue Saturation Value
- CLAHE
- Random Gamma
- Blur
- To Gray
- Image Compression

The image was splitted into Train-Test-Valid sets with `75:10:15` ratio

## Architecture

This is a Convolution Based Model with sequential layers as follows:

- Conv2D with `16` Filters and ReLU activation
- MaxPool2D with pooling 2
- Dropout with probablity of 20%
- Conv2D with `32` Filters and ReLU activation
- MaxPool2D with pooling 2
- Dropout with probablity of 20%
- Conv2D with `16` Filters and ReLU activation
- MaxPool2D with pooling 2
- Dropout with probablity of 20%
- Flatten Layer
- Dense Layer with `512` outputs and ReLU activation
- Dense Layer with `64` outputs and ReLU activation
- Dense Layer with 1 output and Sigmoid activation

This Model used `Binary Cross Entropy` Loss to learn with an `adam` optimizer

## Installation

### You first need to install Tensorflow

#### To install TensorFlow using `pip`, run the following command:
```sh
pip install tensorflow
```

#### To install TensorFlow using `conda`, run the following command:
```sh
conda install tensorflow
```

### Then you have to download the model

Download The model [here](https://github.com/ivanrj7j/Super-Cars-VS-SUVs/releases/download/1.0/model.h5)

Then paste it in your project folder.

## Usage

To use the model

```py
import tensorflow as tf
from tensorflow import keras
from keras.models import load_model
from keras.utils import load_img

#load dependencies

model = load_model('model.h5')
# loading the model 

def predict(image:str):
    """
    Predicts if an image is suv or supercar
    Takes in image path as an argument
    """
    img = tf.expand_dims(tf.convert_to_tensor(load_img(image).resize((256, 256))), 0)
    labels = ['supercars', 'suv']

    return labels[int(model.predict(img, verbose=False)[0])]

predict("path/to/your/image.file")
```

## Contributing

Contributions to this project are welcome! If you have any ideas for improvements or new features, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the **LICENSE** file for more information.
