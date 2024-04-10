# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

## Developed by: RAGAVENDRAN A
## Reg no: 212222230114

## Image Processing:
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("hack.jpg",0)
img_c=cv2.imread("hack.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)

gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)

plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
## Canny Edge Detection:
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## Hough Transform:
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=60,minLineLength=40,maxLineGap=200)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

### Input image and grayscale image

![Screenshot 2024-04-10 104511](https://github.com/ragavanayyadurai/Edge-Linking-using-Hough-Transformm/assets/118749557/5d8f9a1c-71b0-46a9-af6d-096af9fd2050)



### Canny Edge detector output

![Screenshot 2024-04-10 104518](https://github.com/ragavanayyadurai/Edge-Linking-using-Hough-Transformm/assets/118749557/9c2b5789-9ac4-4352-b652-255372f8c995)


### Display the result of Hough transform

![Screenshot 2024-04-10 104525](https://github.com/ragavanayyadurai/Edge-Linking-using-Hough-Transformm/assets/118749557/4af9823d-d7cd-4f5e-bf20-8735def0e575)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.

