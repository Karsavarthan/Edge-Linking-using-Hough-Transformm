# EXP 07
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

### Program
```
NAME: Karsaarthan R R
REG NO : 212223230100
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Taj mahal.jpg')
```
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output

### Input image 

![Screenshot 2025-05-21 202331](https://github.com/user-attachments/assets/78c61917-1e33-477c-b4d2-6b04ac42521d)


### grayscale image

![Screenshot 2025-05-21 202338](https://github.com/user-attachments/assets/e1c6d16c-f107-41d4-9b39-b602747dc250)



### Canny Edge detector output


![Screenshot 2025-05-21 202345](https://github.com/user-attachments/assets/078d1586-b37a-42aa-8fd0-06f258b21a8f)



### Display the result of Hough transform


![Screenshot 2025-05-21 202352](https://github.com/user-attachments/assets/921c5ae1-a566-4b98-9b54-9412d6c506be)



### Result:

Thus the grayscale image , canny edge detector and hence we had displayed the result of hough transform
