# **Finding Lane Lines on the Road** 

## Writeup

---

### Reflection

### 1. Describe your pipeline. 

My pipeline consisted of 5 steps. 
1. I converted the images to grayscale
2. I defined a kernel size and applied Gaussian smoothing
3. I applied Canny Edge Detection to output edge detected image 
4. I defined a region of interest through masking by defining a four sided polygon
5. I then ran Hough on the edge detected masked image to find lane lines


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by
a) classifying left and right lane segments based on their slopes
b) averaging their corresponding slopes and intercepts
c) plotting them using equation of line: y=m_RightSegmentsAverage+bRightSegmentsAverage
                                         y=m_LeftSegmentsAverage+bLeftSegmentsAverage




### 2. Potential shortcomings 


One potential shortcoming is that the the lane lines edge detected won't be robust to sharp road curvature. Or simply it would provide poor performance during lane changes.


### 3. Possible improvements to pipeline

Instead of fitting a line, fitting a curve with a higher degree polynomial might be useful for sharp road curvature. 
Also, different possible polygon mask shapes for sharp right and left turns might serve useful.
