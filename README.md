# Use-GANs-to-create-art

This excersise is from the Kaggle constest "I’m Something of a Painter Myself"

https://www.kaggle.com/competitions/gan-getting-started/overview

The goal of this project is to create a GAN model which can generate images in the style of Monet, this model has two parts: a generator model and a discriminator model, where the generator is trained using a discriminator. The two models will work against each other, with the generator trying to trick the discriminator, and the discriminator trying to accurately classify the real vs. generated images.

As final result, the GAN is going to generate 7,000 to 10,000 Monet-style images.

## Data loading
The data is in two folders, 'monet_jpg' cotains images from Monet paintings, and 'photo_jpg' contain images from photographs. The first step is to load the data from these folders

## Exploratory Data Analysis¶
After loading the data, I'm going to analyze the content of each folder: how many files are and how it looks the data

Number of Monet images: 300
Number of Photo images: 7038

![image](https://github.com/user-attachments/assets/d6476df8-fb85-4eab-9a8f-668c00bc19c0)

![image](https://github.com/user-attachments/assets/346f659a-d376-453a-bad3-52d5fabdb05a)

![image](https://github.com/user-attachments/assets/152224e2-ec7f-4d46-b90c-811b47750c56)

## Analysis - Model building and training
In this exercise I'm goint to use a CycleGAN model with this charateristics:

It has two Generators G: X→Y and F: Y→X

It has two Discriminators Dₓ and Dᵧ to classify real vs. generated images in each domain

The Loss components are:

Adversarial loss for both G and F

Cycle‐consistency loss, which ensures F(G(X))≈X and G(F(Y))≈Y

Identity loss to preserve colour when passing images through the “wrong” generator

Training flow: alternate updates of generators and discriminators, balancing adversarial and cycle losses

For Optimization I'm going to use Adam, and the discrimatores are optimized separately

## Conclusion
In this project, I use a GAN model to create images using the Monet style, the approach was to use a CycleGAN model.
The initial results are good, however the main limitation is the training time, because of the I had to reduce the number of epochs
A future improvement could be increase the number of epochs a change some hyperparameters

