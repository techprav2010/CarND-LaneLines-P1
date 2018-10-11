# **Finding Lane Lines on the Road**

**Finding Lane Lines on the Road**

Describe steps taken to detect lane lines.


[//]: # (Image References)

[imageOriginal]: ./test_images_output/original.png "original"
[imageGrayscale]: ./test_images_output/canny_img_gray.png "canny_img_gray"
[imageGaussian]: ./test_images_output/gaussian_img_gray.png "gaussian"
[imageCanny]: ./test_images_output/canny_img_gray.png "canny_img_gray"
[imageHough]: ./test_images_output/hough_to_line_image.png "hough_to_line_imags"
[imageFinal]: ./test_images_output/final.png "final"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Pipeline follows following steps:

![alt text][imageOriginal]

* original image

![alt text][imageGrayscale]

* convert image into gray scale using openCV. This will help reducing noise.

![alt text][imageGaussian]

* smoothen the image using gaussian filter. This will help reducing noise.

![alt text][imageCanny]

* canny-edge detection to detect edges, corners.  

![alt text][imageHough]

* mask image with region of interest (area where lanes are expected) and detect hough-lines.  

![alt text][imageFinal]

* highlight lane lines: update original image with hough lines overlay. 


### 2. Identify potential shortcomings with your current pipeline
The pipeline does some hard assumptions and will not work always work:
* assumes there is clearly visible lane lines:
* that means it can have issues in the situations like -
  * night time, vehicle abstracting lane lines, road crossings, bad road conditons, water on road, shadows. 


### 3. Suggest possible improvements to your pipeline
* reduce noise  by properly selecting region of interest, effective smoothing.
* detect many shorter lines, and constantly merge them into one. 
* remove effectvely the outlier points/lines

### 4. Real-life issues not considered in the above problem
* Camera with dust or any visibilty issues, can result in poor performance. 
* Area not covered in region of interest due to sharp turns.

