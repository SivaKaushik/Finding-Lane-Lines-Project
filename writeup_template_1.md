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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied guassian blur and then i applied canny edge detection, and then moved on to masking the region we needed instead of the whole area and then applied hough line transformation finally overlapped the red colored lines onto to the image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by taking the slopes associated with the left side and right side and then extrapolated them. Slopes of the left side are negative as y values increase as going down and right side the the negative y gets cancelled out by the negative x so the slope remains positive. 
then for extrpolating we take the average of all the slopes and intercepts on left side and right side and draw line using line function respectively.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be, it doesnt work on curved road like mountainous roads hilly areas.

Another shortcoming could be if the distance between lane changes then area we considered will not be right and that can be a limitation in finding lanes.
if the lane markings are not clearly defined as in the pictures here then that will also be a limitation for the code written.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to trying to concise the draw lines function by using any other means in computer vision if its possible.

Another potential improvement could be to make the code work for the limitation mentioned above.
