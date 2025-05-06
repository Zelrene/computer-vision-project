# RIT - IMGS 621 - Computer Vision Project
The goal of this project is to find the yaw/pitch/roll and position of the camera for images A, B, C, D, and E based on the reference original image. The data and task was provided by Dr. Flip Philips

## Approach
To attempt to find the camera position and orientation, I applied image registration logic through feature detection and extraction to find a homography matrix. Using this matrix, I should be able to calculate the camera orientation. To find the camera position, however, I would need the camera intrinsics to create a calibration matrix. As a result, this code would not have been able to calculate the camera position.

Unfortunately, I was unable to create a homography matrix to calculate camera orientation due to failing to extract and match feature between the reference and target images. I only tested with the original image and Image A because I wanted to make sure my algorithm worked with one image before applying it to all 5 images.

## Files Provided
- images: folder containing the images used
- sky.csv: csv file containing the location of the "stars" or dots on the ceiling