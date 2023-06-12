# Ex.No:8
# <p align="center"> Edge Linking using Hough Transform</p>

## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image
<br>


### Step2:
Find the edges in the image using canny detector and display
<br>

### Step3:
Detect points that form a line using HoughLinesP
<br>

### Step4:
Draw lines on the image
<br>

### Step5:
Display the result
<br>
<br>

## Program:
```Python
# Read image and convert it to grayscale image
import cv2 
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("br.jpg",0)
img_c=cv2.imread("br.jpg",1)
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Gray Image')
plt.imshow(img)
plt.show()
# Find the edges in the image using canny detector and display
canny=cv2.Canny(img,120,150)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Canny')
plt.imshow(canny)
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(canny,1,np.pi/180,50,20,2)

# Draw lines on the image
blank_image = np.ones(img.shape, dtype=np.uint8)
for lin in lines:
    x1,y1,x2,y2=lin[0]
    cv2.line(blank_image,(x1,y1),(x2,y2),(255,0,0),2)
    
# Display the result
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Hough Transform')
plt.imshow(blank_image)
plt.show()

```
## Output

### Input image and grayscale image

![ss1](https://user-images.githubusercontent.com/75235704/171360937-d208dad9-6cd5-4f5d-ad95-846c5ca65fee.png)

<br>
<br>
<br>
<br>

### Canny Edge detector output
![ss2](https://user-images.githubusercontent.com/75235704/171360974-1ed62a83-5f5e-443c-af70-017b71601140.png)


<br>
<br>
<br>
<br>


### Display the result of Hough transform

![ss3](https://user-images.githubusercontent.com/75235704/171361014-da06e595-0fbb-4bb0-9cec-c71c7028a9db.png)

<br>
<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
