# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/gray_solidWhiteCurve.jpg "gray"

[image2]: ./test_images_output/Gaussian_blurring_solidWhiteCurve.jpg "Gaussian"

[image3]: ./test_images_output/Canny_edges_solidWhiteCurve.jpg "Canny"

[image4]: ./test_images_output/masked_edges_solidWhiteCurve.jpg "mask"

[image5]: ./test_images_output/Hough_lines_solidWhiteCurve.jpg "Hough"

[image6]: ./test_images_output/final_solidWhiteCurve.jpg "final"

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of 6 steps:

1. Read in the image and convert to grayscale
![alt text][image1]

2. Define a kernel size for Gaussian smoothing / blurring and run it 
![alt text][image2]

3. Define parameters for Canny edge detection and run it
![alt text][image3]

4. Define a four sided polygon to mask and run it
![alt text][image4]

5. Define the Hough transform parameters and run it
![alt text][image5]

6. Overlay Hough lines with initial image
![alt text][image6]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:

1. An average value is calculated for the slope, x, and y.
2. A final line is drawn using the following function. 
![equation](http://www.sciweavers.org/upload/Tex2Img_1519281586/render.png)  
Note: throw out steep vertical slopes to avoid NaN error!

### 2. Potential shortcomings with my current pipeline
It can't deal with curved lane, as in the "Challenge" part.

### 3. Possible improvements to my pipeline
1. Investigate methods to address the curved lane issue
2. Current solution is kind of static (e.g., manually trying out different parameters). How to make the algorithm robust and adaptive to any online changes such as unexpected cameral movement?
