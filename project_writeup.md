# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

1. Convert the images to grayscale
2. Apply Gaussian smoothing while adjusting the kernel size and found 3 to be the most suiting
3. Use Canny filter to do edge detection
4. Defined a 4-sided polygon mask to find the region that we care about
5. Use the Hough transform to find the lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by increasing the max_line_gap from 50 to 100.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is a railing or some other objects which also contain lines that are close to the lane lines. I think it would be important to have a tight polygon mask in that case. 

Another shortcoming could be in darker or dimmer situations, it would be hard to see the lines or at least hard enough to see that far to have a good understanding of if the road curves or not.

I also see that there are certain lines that are not the lane lines being outlined.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to make sure the polygon mask is as tight as possible so you don't see other lines that could be confused as lane lines.

Another potential improvement could be to tweak the parameters more in each of the 5 steps above.
