# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : DARIO G
Register Number : 212222230027
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('SF23.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('SF23.jpg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
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
### Output

### Original Image
![Screenshot 2024-04-23 105330](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/5d82af4a-7818-4e43-9d22-d2b361be9d54)


### Global Thresholding
![Screenshot 2024-04-23 105351](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/66c5b868-33c2-4b83-9f40-6de348777b4b)

![Screenshot 2024-04-23 105407](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/ec41c8fd-4ab4-46cf-baef-009013ecc3b7)

![Screenshot 2024-04-23 105423](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/a10beece-c2d5-4b67-892d-92a0ec68455f)

![Screenshot 2024-04-23 105443](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/bee4758f-220b-4cb5-aaf1-48e5d71be719)

![Screenshot 2024-04-23 105503](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/8bbad59a-b91b-4ff8-987e-70c44ee36e20)







### Adaptive Thresholding
![Screenshot 2024-04-23 105513](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/edd34647-f167-4045-8e95-160bca9d3b19)

![Screenshot 2024-04-23 105523](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/77c74bc4-6880-480e-bd7f-17a1dbbc498c)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-23 105536](https://github.com/DARIOGEORGE/Thresholdingg/assets/118704873/2d890d72-3842-4b60-bf03-86361d03f9f8)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
