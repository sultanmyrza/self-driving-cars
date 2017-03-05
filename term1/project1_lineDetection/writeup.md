#**Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect  work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pip line
 1)	apply gaussian blur on image in order to remove anamaly pixels
 2) convert image to hsv for color extraction
 3) create mask for white color (to extract white lanes from hsv image)
 4) create mask for yellow color (to extract yellow lanes from hsv image)
 5) create mask for region of interest (to work only on interested part of image)
 6) combine all masks (yellow + white + region + origial_image = combo)
 7) apply canny algo on combo image -> get images with edges
 8) apply probalistic hough lines on image with edges -> get gough lines
 9) separate lines to left_lines and right_lines
 10) strech left and righ lines
 11) draw extrapolated left and right lines on blank image
 12) combine original image and image with lines using ```cv2.addWeighted()``` function


###2. Identify potential shortcomings with your current pipeline

- color mask work not good enough because of shadows on the road

###3. Suggest possible improvements to your pipeline
 + A possible improvement would be to make darker image before applying color mask

 + Another potential improvement could be to save last N detected lines and generate
lines from last N lines if no line was detected

