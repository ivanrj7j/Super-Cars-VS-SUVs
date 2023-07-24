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

[will be added later]

## Installation

[will be added later]

## Usage

[will be added later]

## Contributing

Contributions to this project are welcome! If you have any ideas for improvements or new features, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the **LICENSE** file for more information.
