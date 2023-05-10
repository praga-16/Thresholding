# Thresholding of Images
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

Use Otsu's method to segment the image.

### Step 6:

Display the results.

## Program
```python
Developed By: Pragatheesvaran AB
Register No : 2122221240039
``` 

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt


# Read the Image and convert to grayscale

image=cv2.imread("Sasuke.png",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("Sasuke.png",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()



```
## Output

### Original Image
![g](https://github.com/praga-16/Thresholding/assets/95266924/33a9623e-a5df-4036-ab5f-b98134dc4f58)



### Global Thresholding
![binary](https://github.com/praga-16/Thresholding/assets/95266924/c0cbb5cd-b536-412c-909f-8de779af79e2)
![binary inverse](https://github.com/praga-16/Thresholding/assets/95266924/b585f2a3-d320-44f0-a10e-db2f73f7210d)
![t0](https://github.com/praga-16/Thresholding/assets/95266924/46caa545-2e9c-4590-a0da-b824f861adbd)
![t inverse](https://github.com/praga-16/Thresholding/assets/95266924/6a88a47c-9eaa-4390-a249-892b1361bf81)
![truncate](https://github.com/praga-16/Thresholding/assets/95266924/ff6935a0-b495-43d0-a1a5-f101da82f422)



### Adaptive Thresholding
![mean](https://github.com/praga-16/Thresholding/assets/95266924/3f66b22c-9fe0-4a31-9efb-783047391b97)
![gauss](https://github.com/praga-16/Thresholding/assets/95266924/e06a8a32-7cc8-44cb-adc4-c11055e74655)


### Optimum Global Thesholding using Otsu's Method
![otsu](https://github.com/praga-16/Thresholding/assets/95266924/e5251c7d-3e50-4597-af5e-e6c8e01f9aa4)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

