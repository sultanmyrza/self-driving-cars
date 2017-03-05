#**Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect  work in a written report


###1. Pipline description
 * 	apply gaussian blur on image in order to remove anamaly pixels
 *  convert image to hsv for color extraction
 *  create mask for white color (to extract white lanes from hsv image)
 *  create mask for yellow color (to extract yellow lanes from hsv image)
 *  create mask for region of interest (to work only on interested part of image)
 *  combine all masks (yellow + white + region + origial_image = combo)
 *  apply canny algo on combo image -> get images with edges
 *  apply probalistic hough lines on image with edges -> get gough lines
 *  separate lines to left_lines and right_lines
 *  strech left and righ lines
 *  draw extrapolated left and right lines on blank image
 *  combine original image and image with lines using ```cv2.addWeighted()``` function


###2. Identify potential shortcomings with your current pipeline

- color mask work not good enough because of shadows on the road

###3. Suggest possible improvements to your pipeline
 + A possible improvement would be to make darker image before applying color mask

 + Another potential improvement could be to save last N detected lines and generate
left and right lines from last N detected lines if no line was detected

