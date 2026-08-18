# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
## Step 1: 
Import the required libraries such as cv2, numpy, and matplotlib.pyplot.

## Step 2:
Read the input image using cv2.imread() and convert it into grayscale if required.

## Step 3:
Define a structuring element using cv2.getStructuringElement(). The structuring element determines the shape and size of the morphological operation.

## Step 4:
Apply the erosion operation using cv2.erode(). Erosion reduces the size of white regions and helps remove small unwanted objects or noise.

## Step 5:
Apply the dilation operation using cv2.dilate(). Dilation expands white regions and helps enhance or restore objects in the image.

## Step 6:
Display the original, eroded, and dilated images using plt.imshow() and provide suitable titles.

## Step 7:
Use plt.show() to display all the processed images..

 
## Program:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

text = input("Enter the text ")

image = np.zeros((300, 800), dtype=np.uint8)


cv2.putText(
    image,
    text,
    (30, 150),
    cv2.FONT_HERSHEY_SIMPLEX,
    2,
    255,
    5
)


kernel = cv2.getStructuringElement(
    cv2.MORPH_RECT,
    (5, 5)
)


erosion = cv2.erode(image, kernel, iterations=1)


dilation = cv2.dilate(image, kernel, iterations=1)

plt.figure(figsize=(12, 8))

plt.subplot(1, 3, 1)
plt.imshow(image, cmap="gray")
plt.title("Original Text")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(erosion, cmap="gray")
plt.title("Eroded Text")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(dilation, cmap="gray")
plt.title("Dilated Text")
plt.axis("off")

plt.tight_layout()
plt.show()


```
## Output:
<img width="1359" height="248" alt="image" src="https://github.com/user-attachments/assets/b81bb360-2600-4db7-af29-77b5f76ee5ac" />


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
