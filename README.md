# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules.
<br>

### Step2:
Import the image to operate on.
<br>

### Step3:
Convert the imported image from BGR to GRAYSCALE.
<br>

### Step4:
Find the edges using canny edge detector and display the image.
<br>

### Step5:
Detect the points that form a line using hough transform.
<br>

### Step6:
Draw the lines on the image.
<br>

### Step7:
Display the output.
<br>

### Step8:
End the program.
<br>

## Program:
#### Developed by: Manoj Guna Sundar Tella.
#### Register Number: 212221240026.
```Python


# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(smoothImage,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(cannyEdges)
plt.show()


```
## Output

### Input image and grayscale image
![img1](https://user-images.githubusercontent.com/94883876/169661444-bf827657-5d8a-4618-9d76-f13a7fc890ee.jpeg)

<br>
<br>
![img2](https://user-images.githubusercontent.com/94883876/169661464-51b1044d-c4eb-4e2b-a0bc-ecb9f46c4cee.jpeg)

<br>
<br>

### Canny Edge detector output
![img3](https://user-images.githubusercontent.com/94883876/169661478-dfd4cf1e-2cc0-49b5-9233-35f836793702.jpeg)

<br>
<br>
<br>
<br>


### Display the result of Hough transform
![img4](https://user-images.githubusercontent.com/94883876/169661484-ef4c743f-21c9-4b01-a9e0-2384124d11bf.jpeg)


<br>
<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
