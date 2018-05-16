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

My pipeline consisted of 6 steps:
* turn the image into gray scale
* add Gaussian Blur
* use Canny to calculate the edges
* mask the image with region of interest
* use hough_lines() function to get all lines, do average and extrapolate the lines in draw_lines() function
* combo the lines with orignal image


In order to draw a single line on the left and right lanes, I modified the draw_lines() function:
* initiate lines collections of left and right side 
* distinguish the lines on the left and right by slope, add them to relevant collections
* average values of collections to get one left line, and one right line
* define y values (bottom/center+70 px of the image) of bottom and top points, and calculate x values by slope
* draw the left/right lines


### 2. Identify potential shortcomings with your current pipeline

Potential shortcomings:
* Hard coding with pixel values in current solution, problems will happen when image resolution or view angle change
* Distinguish left and right lines by slope, problems will happen when car changes lane
* Identify lane lines by length and gap values, problems will happen when other similar shape of lines appear (the optional challenge)

### 3. Suggest possible improvements to your pipeline

Possible improvements:
* define more detailed criteria to distinguish lane lines, with different conditions (light, texture of the road, turns, lane change.. etc)
* use Deep Learning to train machine to recognize lane lines?


