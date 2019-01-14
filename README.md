# Detecting-Cancer-in-Gigapixel-Pathology-Images
As a part of a class project, I worked on a Cancer Detection problem. 

## Motivation

1. We can radically reduce the misdiagnosis rate for common procedures such as that is tissue pathology diagnosis using basic deep learning techniques and simple neural net architectures. 
2. Visual detection is tedious and error-prone.
3. Tissue samples to be examined are volumes, and can give us many sample images when sliced.
4. Some tumors can be really small, causing errors in human reading. 
5. Expertise is rare - Pathologists have many patients and limited time to spend on each slide - hence, mistaken happen. 

## Goal

Given a collection of training data, create a model that outputs a heatmap showing regions in the biopsy image that are likely to contain cancer. 
The goal is to assistand not completely replace pathologists. 

## Data Available

- 400 WSI (whole slide images) collected independently from two medical centers in the Netherlands.
- 7 magnification levels available per slide, up to 128x.
- For each slide, the ground truth given are masks of the WSI (and of same dimensions as the WSI).
- WSI's and Masks available as .tif files. 

## Approach

# Pre-Processing 

- Apply monotone masks to WSI's
- Calculate percentage tissue in each slide and only take the ones that have at least some amount of tissue. 

# Extracting samples and assigning labels

- Slide a fixed-size window over the slide at a fixed zoom level. 
- Look at the corresponding window in the mask, and assign label as 1 if at least 1 pixel is non-0 in this mask patch. 

# Data is quite imbalanced. Try approaches such as the following to make it balanced : 

- Oversampling
- Downsampling
- Augmentation

Finally, divide the data into train, test and val, define an evaluation metric suitable for the problem, and evaluate results by visualising them on a heatmap. 

Link to full video despcription of the project with code explanation: https://www.youtube.com/watch?v=8QrkNKpMl9o&t=25s

