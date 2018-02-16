# Finding Lane Lines on the Road 

<img src="output_images/Found Lines.png" width="300" alt="Combined Image" /> <img src="output_images/Full Pipeline Example.png" width="300" alt="Combined Image" />


Skills
---
* Python
* OpenCV


Overview
---

This project was completed as an assignment for Udacity's Self Driving Car Nano Degree [![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive). The jupyter notebook walks step by step through the process of identifying lane lines in a video stream, including image distortion correction, Sobel edge detection, perspective transform, sliding window search, and more. 

The provided videos and calibration images can be found [here](https://github.com/udacity/CarND-Advanced-Lane-Lines).


Dependencies
---
This project was built using the anaconda _carnd-term1_ environment available [here](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/doc/configure_via_anaconda.md)


Algorithm
---

1. Use calibration images to establish distortion correction factors for the camera, and undistort all incoming images. 

2. Use Sobel edge detection on a grayscale image to identify feature (lane line) boundaries 
			
3. Use color value thresholding (S channel of HLS colorspace) to identify features of interest (lane lines)
		
4. Stack the binary images from steps 2 and 3 

5. Establish a perspective transform and apply it to all incoming stacked binary images
		
6. Perform a sliding window search to identify the lane lines

7. Fit identified lines to polynomial, calculate key values (radius of curvature and lane position), and create lane mask. Transform mask back into original image perspective and overlay on the images along with calculated values. 
 

 Contents
 ---

* Advanced_Lane_Finder.ipynb
    * jupyter notebok containing all code
* project_video.mp4
    * raw video to be processed
* project_video_output.mp4
    * processed video with lane lines identified
    

* camera_cal
    * contains chessboard calibration images for camera
* output_images
    * contains output of intermediate processing steps from the step-by-step breakdown of pipeline architecture
* test_images
    * contains individual test images for demonstration of intermediate processing steps
