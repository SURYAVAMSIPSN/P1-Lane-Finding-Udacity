# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

The project was done in the following steps. 
1. An image was taken and converted to grayscale. Then, gaussian noise was removed from it. 
2. Using canny edge detection, sharp edges, namely the lane markings, were detected on the image. 
3. Then hough transform was used to draw line segments on the lane edges. A masking was done to only consider the region of interest (lower 
half triangle of the given image)
4. This was tested on both an image as well as videos (stream of images)
5. The draw_lines function was modified such that the line segments were made into solid lines, by extrapolating (estimating) the position
of the lines on the image, unsing the concepts of equations of a line and slope and intercepts. 


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be that the camera has to be fixed in order to perform proper masking and obtaining the region of interest. 
This means that if the camera were tilted facing upward a little, due to disturbances, the whole region of interest co-ordinates need to be changed. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to develop a generic algorithm that can accomodate disturbances and be robust enough to detect the lanes. 
