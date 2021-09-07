# **Finding Lane Lines on the Road** 
### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale using gray(), then I used gaussian_blur() to remove noise from the image. Canny() has been used to apply canny transformations to the image and region_of_interest() has been used to keep only the region of image which is within the defined region. Finally, hough_lines() has been used to draw hough lines on the image.    

In order to draw a single line on the left and right lanes, I modified the draw_lines() function to save coordinates for left and right lanes in (xl,yl) and (xr,yr) respectively. Then I calculated slopes for left and right lanes using maximum and minium coordinates of xl, yl, xr and yr. Finally, I interpolated the lines to coordinates of mask using slopes calculated above. 

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be that the pipeline does not work properly when the car encounters a curvature. 

Another shortcoming could be the pipeline might not work perfectly while working with shadows on the road and this pipeline does not differentiate between different colors of lanes. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to look at the lanes from birds' view using perspective transform in order to solve the problems encountered during curvature. 

Another potential improvement could be to find a way to differentiate between different colors of lanes using color gradients and different color schemes such has HLS, HSV might give better output. 
