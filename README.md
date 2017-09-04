# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. My pipeline.

My pipeline consisted of 5 steps. First, I converted the images to grayscale.

![gray.png](http://upload-images.jianshu.io/upload_images/3623720-45b171f4c4421c71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Then I use Gaussian blur to make the noises in image smooth.

![gauss.png](http://upload-images.jianshu.io/upload_images/3623720-b162f0017682ae13.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Next, I use canny detection to detect the edge of the image. 

![edge.png](http://upload-images.jianshu.io/upload_images/3623720-a8f5eea30f305608.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Then I cut the region of interest out of the image. 

![roi.png](http://upload-images.jianshu.io/upload_images/3623720-fee0dff296844319.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
Then I use hough algorithm to detect lines in the image. 

![line.png](http://upload-images.jianshu.io/upload_images/3623720-48b537534f276c9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

At last I combine this lines into the origin image to get the final image in which there is a lane line.

![combine.png](http://upload-images.jianshu.io/upload_images/3623720-d330f8c2d969b88e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

In order to draw a single line on the left and right lanes, I modified the draw_lines() function. I compute all the slope and bias about left and right lines, then I delete some unreasonal results. At last I get the mean of the slopes and bias and I draw a line according to the mean slope and bias.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be robustious, it can only detect the line in the center of the screen. 

Another shortcoming could be that it will fail when entering into curve or circumstance becoming complex, it could not detect any line.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to change the parameters to overcome some situations.

Another potential improvement could be to use other technology to do this job.
