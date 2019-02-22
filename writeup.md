# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline consisted of 5 steps. 
1.I seperate left and right lines from lines that hough function found.
2.I delete some of the rather 'flat' lines from left and right lines that I seperated from step 1. Flat lines' derivatives is small, that's how I find them.
3.Then I use polyfit function from numpy to fit a line in order to find m and b for y=m*x+b.

4.Then I caluate x value of start point and end point with y value of 540 and 320.
5.Then I draw a line with two points that I caluate from step 4.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane line is a curve.

Another shortcoming could be when there is a in front of my camera, my algorithm may not be able to see, therefore may not be able to create the lane lines. 


### 3. Suggest possible improvements to your pipeline

When light condition changes, my algorithm may encounter some mistakes, it may be helpful to use Hue of HLS colorspace to seperate lane lines, because light condition hardly influence hue.
 
Another potential improvement could be to use a quadratic function to fit lane lines instead of a line, thus when lane line is a curve, algorthm can still detect it correctly.