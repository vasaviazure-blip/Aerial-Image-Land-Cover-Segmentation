# Aerial Image Land-Cover Segmentation

## Overview

This project implements a pixel-wise land-cover segmentation system for aerial images using machine learning and image-processing techniques.

The aim is to classify individual pixels into different land-cover categories based on colour, texture, and spatial information.

## Classes

The model classifies pixels into five land-cover categories:

- Building
- Road
- Tree
- Vehicle
- Grass

## Methodology

The project follows these main stages:

1. Load and preprocess aerial images.
2. Extract pixel-level visual features.
3. Train a Gaussian Naive Bayes classifier.
4. Predict the land-cover class for each pixel.
5. Apply spatial smoothing to reduce noisy predictions.
6. Visualise and evaluate the segmentation results.

## Features

Nine pixel-level features are used for classification, including:

- RGB colour features
- HSV colour features
- Excess Green Index (ExG)
- Redness-to-Greenness ratio
- Local texture information

These features provide colour and spatial information that helps distinguish between different land-cover classes.

## Machine Learning Model

### Gaussian Naive Bayes

A Gaussian Naive Bayes classifier is used as the main pixel-classification model.

The model estimates the probability of each land-cover class based on the extracted features and assigns the most probable class to each pixel.

## Spatial Smoothing

A **7 × 7 majority-vote filter** is applied after the initial pixel classification.

This helps:

- Reduce isolated incorrect predictions
- Remove small noisy regions
- Improve spatial consistency
- Produce cleaner segmentation maps

## Testing

The project includes testing masks and visualised segmentation results.

Example files:

```text
test_masks/
├── test_mask_01.png
├── test_mask_01_visualised.png
├── test_mask_02.png
└── test_mask_02_visualised.png
