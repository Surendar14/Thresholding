# EX-9--Thresholding
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
![1](https://user-images.githubusercontent.com/75235759/234522671-e1ed49d5-a6e6-4ac8-869e-b3f38c9bba3f.png)



### Global Thresholding
![2](https://user-images.githubusercontent.com/75235759/234522791-882c3683-8279-47a2-818a-e6e8617834aa.png)

![3](https://user-images.githubusercontent.com/75235759/234522885-39ae4df4-4e04-46b7-bcc7-0ebbafa995e3.png)

![4](https://user-images.githubusercontent.com/75235759/234522951-3bedd3c9-9092-4f0c-96ef-1f8358320bda.png)

![5](https://user-images.githubusercontent.com/75235759/234523068-d9f7f406-ba41-4df2-a42f-d3b406d09037.png)

![6](https://user-images.githubusercontent.com/75235759/234523255-bb682ee2-391e-499b-879a-084ab2d5cee2.png)

### Adaptive Thresholding

![8](https://user-images.githubusercontent.com/75235759/234523447-a99abff2-0661-4547-ae02-13386346032b.png)

![9](https://user-images.githubusercontent.com/75235759/234523560-393b3d27-35f7-4a24-b280-0c6b05a5c9bf.png)

### Optimum Global Thesholding using Otsu's Method
![7](https://user-images.githubusercontent.com/75235759/234523402-2ef816b2-f3c6-4c9b-829c-c876363fc8de.png)



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
