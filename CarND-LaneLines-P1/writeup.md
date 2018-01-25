# **Finding Lane Lines on the Road** 



---

**Finding Lane Lines on the Road**

The goal of this project is to design a pipeline that finds lane lines on the road..



[//]: # (Image References)

[image1]: ./Images_Writeup/Color.png "Color"
[image2]: ./Images_Writeup/Gray.png "Grayscale"
[image3]: ./Images_Writeup/Gaussian.png "Gaussian"
[image4]: ./Images_Writeup/Canny.png "Canny"
[image5]: ./Images_Writeup/ROI.png "ROI"
[image6]: ./Images_Writeup/LaneMark.png "LaneMark"


---

### Reflection

### 1. Description of the pipeline.
 
My pipeline consisted of 11 steps. The steps are discussed below:

![alt text][image1]

1. The color images are converted to gray scale

![alt text][image2]
 
2. Gaussian filter is used for smoothing

![alt text][image3]

3. Applied Canny algorithm to detect sharp edges

![alt text][image4]

4. Marked the region of interest (ROI) to filter out and only focus on lane lines

![alt text][image5]

5. Applied Houghline function to find out the straight lines inside ROI
6. Separate left and right lanes using slope based threshold
7. Find out the coefficients (m,b) of straight lines
8. Averaging the coeffients with the previous frame data for smoothing out the lane marks
9. Find out the corresponding X values from MinY and MaxY of the image
10. Draw lines with specific color and thickness
11. Paste the lane marks on the color image

![alt text][image6]




### 2. Potential shortcomings with the current pipeline


Potential shortcomings would be 

-If the roads are curved as I am using y = mx + c (straight line) to draw (big limitation)

-It might now work accurately if there is less sunlight or to flashy.

-During lane change of my vehicle might cause unexpected behaviour while detecting the lanes





### 3. Possible improvements to the current pipeline

-Need to use polynomial function instead of simple straight line

-Should be more robust in terms changing colors of the image 

-The algorithm should tackle the lane change of both of my car and the car in front 
