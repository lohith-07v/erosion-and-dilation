# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create a blank image using NumPy.

### Step 3:

Insert text onto the image using OpenCV's text drawing function.

### Step 4:

Display the original image.

### Step 5:

Create a structuring element (kernel) of suitable size.

### Step 6: Image Erosion

- Apply the erosion operation using the created kernel.
- Remove pixels from the boundaries of foreground objects.
- Display the eroded image.

### Step 7: Image Dilation

- Apply the dilation operation using the same kernel.
- Add pixels to the boundaries of foreground objects.
- Display the dilated image.

### Step 8:

Compare the original, eroded, and dilated images.

## Program
Step 1:Import the required libraries: OpenCV, NumPy, and Matplotlib.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
Step 2: Create a blank image
```
image = np.zeros((300, 600), dtype=np.uint8)
```
Step 3: Insert text onto the image
```
cv2.putText(image, 'OpenCV', (50, 180), cv2.FONT_HERSHEY_SIMPLEX,
            4, 255, 8, cv2.LINE_AA)
```
Step 5: Create a structuring element (kernel)
```
kernel = np.ones((5, 5), np.uint8)
```
Step 6: Image Erosion
```
eroded = cv2.erode(image, kernel, iterations=1)
```
Step 7: Image Dilation
```
dilated = cv2.dilate(image, kernel, iterations=1)
```
Step 4 & 8: Display and compare original, eroded, dilated images
```
titles = ['Original Image', 'Eroded Image', 'Dilated Image']
images = [image, eroded, dilated]

plt.figure(figsize=(15, 5))
for i in range(3):
    plt.subplot(1, 3, i + 1)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()
```
## Developed By

**Name:Lohith V** 
**Register No:212225230154**

## Output

### Original Image



![alt text](<Screenshot 2026-08-19 180300.png>)




- A text image containing characters is displayed.
- The image serves as the input for morphological processing.

### Erosion



![alt text](<Screenshot 2026-08-19 180317.png>)




- Original image is displayed.
- Eroded image is displayed.
- The thickness of the characters is reduced.
- Object boundaries shrink inward.

### Dilation



![alt text](<Screenshot 2026-08-19 180331.png>)




- Original image is displayed.
- Dilated image is displayed.
- The thickness of the characters increases.
- Object boundaries expand outward.

## Result

Thus, the morphological operations **Erosion** and **Dilation** are successfully implemented using OpenCV.
