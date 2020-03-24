# **Finding Lane Lines on the Road** 

## Writeup Template


### Description

Approach to my pipeline started with trying two approaches in mind 
1: masking of yellow and white lanes.
2: Graying out the image

I used both images to find out the better tuning parameters for canny detector.

The code goes on to reduce the noise in the image using gaussian function. To find the existing lines it uses canny edge detector. With the region of the interest around the lanes, hough transform is used to vote for the slopes of lanes that forms the lanes. The code uses extrapolation to draw line on the image. The simple extrapolation is not sufficient because there are lines with different slopes that doesn't form the lane lines. The extrapolation function is updated to split lanes between left and right using slopes and the position of the x coordinate of the image. Then the function uses the average of the coordinates and the slope to draw the line.



But the existing functions won't work if there are many shadows on the image or the if the car is making a turn it will be hard for the car to detect lines. The available algorithm will also failt in varying light conditions and also if the lanes cannot be perfectly seen.


Few possible improvements can be:
1: Using diferent colorspace
2: Predicting the second lane with the help of one lane
3: Predicting the lanes using lanes from previous frames