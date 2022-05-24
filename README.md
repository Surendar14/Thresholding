# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)

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
    plt.figure(figsize=(5,5))
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
## OUTPUT:

### Original Image and Grayscale Image
![Screenshot (76)](https://user-images.githubusercontent.com/75235759/170044786-3ca2be58-be43-4541-81f9-7d288b50bd7f.png)


### Global Thresholding
![Screenshot (77)](https://user-images.githubusercontent.com/75235759/170044938-a6f18ced-3f17-4443-9732-6398948e34c5.png)
![Screenshot (80)](https://user-images.githubusercontent.com/75235759/170044951-caac2ddc-7a36-469f-8301-ef77837bde35.png)
![Screenshot (78)](https://user-images.githubusercontent.com/75235759/170044962-c728215c-14ea-44aa-aa89-b1ecb710e66a.png)
![Screenshot (81)](https://user-images.githubusercontent.com/75235759/170044975-0b0bd526-493f-4b6e-b369-c0d41701bb70.png)
![Screenshot (79)](https://user-images.githubusercontent.com/75235759/170045004-1cd7fb7a-ca17-4071-aee8-080b26b6cfd2.png)

### Adaptive Thresholding
![Screenshot (83)](https://user-images.githubusercontent.com/75235759/170045166-02f87580-5af4-43da-8e77-062ed8dce6bf.png)
![Screenshot (82)](https://user-images.githubusercontent.com/75235759/170045171-f60bd8b5-eeb0-45fe-ad38-58671de0ffe0.png)

### Optimum Global Thesholding using Otsu's Method
![Screenshot (84)](https://user-images.githubusercontent.com/75235759/170045219-c48d14e5-84d9-4426-b993-fa329abcc7cf.png)


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
