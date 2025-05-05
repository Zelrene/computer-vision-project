# RIT - IMGS 621 - Computer Vision Project
The goal of this project is to find the yaw/pitch/roll and position of the camera for images A, B, C, D, and E based on the reference original image. The data and task was provided by Dr. Flip Philips

## Approach
To attempt to find the camera position and orientation, I applied image registration logic through feature detection and extraction to find a homography matrix. Using this matrix, I should be able to calculate the camera orientation. To find the camera position, however, I would need the camera intrinsics to create a calibration matrix. As a result, this code would not have been able to calculate the camera position.

Unfortunately, I was unable to create a homography matrix to calculate camera orientation due to failing to extract and match feature between the reference and target images. I only tested with the original image and Image A because I wanted to make sure my algorithm worked with one image before applying it to all 5 images.

## Files Provided
- images: folder containing the images used
- sky.csv: csv file containing the location of the "stars" or dots on the ceiling

## Written Files
The following are files I created when doing this project. It consists of two .mat files and two .mlx (live script) files.
- preprocessing.mlx
This file created the two .mat files provided. This file handles denoising and the first attempt of image registration.

To denoise the image, binarized the images and used erosion and dilation.

The original attempt of registration I did was using ORB feature detection and then SURF feature detection. Both resulted in incorrect feature matching as I focused on the "stars" or circular dots, and each circular dot were identical. Another attempt I did was creating bounding boxes to focus on detecting the rectangular light fixtures instead.

- processed_imgs.mat
- rawdata.mat

- processing.mlx
This file was my second attempt in image registration. Using the bounding boxes calculated from preprocessing.mlx, I bounded the feature detection to the rectangular bounds. Instead of ORB or SURF, I used Harris corner detection because I believe they would be preferred when targetting rectangluar (edges and corners) features.

I created this file, mainly because preprocessing.mlx became crowded and messy. As a result, it became more for denoising and saving necessary variables to be used in this file.