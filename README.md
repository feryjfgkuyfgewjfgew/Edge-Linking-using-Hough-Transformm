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
## PROGRAM:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Screenshot 2025-04-21 183805.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image

![Screenshot 2025-04-21 183805](https://github.com/user-attachments/assets/00905d39-3b31-4692-b268-41c67d77ca56)
![Screenshot 2025-04-21 183916](https://github.com/user-attachments/assets/7258a312-7cca-4a3f-ab9a-4b5ed4681131)


### Canny Edge detector output
![Screenshot 2025-04-21 183924](https://github.com/user-attachments/assets/b79e9364-4ef5-47da-8386-1e0c08d97c46)


### Display the result of Hough transform
![Screenshot 2025-04-21 183931](https://github.com/user-attachments/assets/75e58748-ca9f-41d5-8005-89dd2bf663ad)

