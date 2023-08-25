# Histopathology Image Retrieval
![Histopathology Image Retrieval](https://production-media.paperswithcode.com/methods/Screenshot_2021-03-15_at_19.58.32_ENGHInW.png)
## Description

This project implements an image retrieval system for histopathology images using the BYOL (Bootstrap Your Own Latent) self-supervised learning model. The goal is to retrieve similar histopathology images given a query image.

## Model

BYOL is a self-supervised learning approach that trains a neural network to predict its own embeddings using an online encoder and a target encoder. The online encoder is tasked with predicting the output of the target encoder, which has a slow-moving average to ensure consistency. 

This allows BYOL to learn semantic feature representations from unlabeled images in a self-supervised manner, without the need for human-annotated labels.

In this project, a BYOL model pre-trained on ImageNet is used as the image encoder. Images are passed through the model to generate BYOL feature vectors that are used to index and retrieve similar histopathology images.

## Datasets  

The model is trained and evaluated on the following histopathology image datasets:

- [BracS](https://www.bracs.icar.cnr.it/) - Breast Cancer Histopathology Image Dataset
- [CRC](https://warwick.ac.uk/fac/cross\_fac/tia/data/extended\_crc\_grading/) - Colorectal Cancer Histopathology Images  
- [BATCH](https://iciar2018-challenge.grand-challenge.org/Dataset/) - BreAst Cancer Histology Challenge Dataset

## Usage

The image retrieval system allows uploading a query histology image. It indexes through the dataset encodings to find the most similar images based on the BYOL features. The top k retrieved images are returned, ranked by similarity.

The project provides code to train the BYOL encoder and utilities to index and search the datasets.

## References

[BYOL Paper](https://arxiv.org/abs/2006.07733)
