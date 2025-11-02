# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
#Developed by : PRIYANKA K
#Register No: 212223230162

# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale
image = cv2.imread('dog.png')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')



# Use Global thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)



# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
![exp8](https://github.com/user-attachments/assets/477928f5-9055-4ae9-bede-0072cc96f602)

### Global Thresholding

<img width="224" height="240" alt="image" src="https://github.com/user-attachments/assets/61ff94c7-74cd-4602-822e-51557bad8e12" />

### Adaptive Thresholding

<img width="251" height="242" alt="image" src="https://github.com/user-attachments/assets/b41bce02-daf5-4f7a-8f5c-436c634cc82f" />

### Optimum Global Thesholding using Otsu's Method

<img width="217" height="247" alt="image" src="https://github.com/user-attachments/assets/9033f559-7f55-482e-a131-0f6fd84f76ac" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
