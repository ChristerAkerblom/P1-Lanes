# **Finding Lane Lines on the Road** 


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline consists of of the following steps.
* Convert the image to gray scale and applying a gaussian blur filter to remove noise
* A four sided polygon was used to mask ROI
* A Canny edge detection filter was applied on the ROI followed by a Hough transform to filter out lines
* In order to draw a single line on the left and right lanes, I modified the draw_lines() function by sorting lines into leftside lines (slope < 0) and right side lines (slope > 0). Also lines close to horizontal (small slope) were rejected. A single line for each side where the projected on the identified lines using the linspace function.


### 2. Identify potential shortcomings with your current pipeline
The follwing shortcomings have been identified.
* The pipeline has no memory i.e. knowledge from the previous image is not used in the next.
* Regions where lines are not detected or is of poor quality should be identified and handled. 


### 3. Suggest possible improvements to your pipeline
A possible solution to the shortcomings could be:
* Apply a low pass filter to reduce variations of the line between images
* Identify regions where little poor line information are available and use dead reackoning 

