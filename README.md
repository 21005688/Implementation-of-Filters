# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().



### Step2
Convert the saved BGR image to RGB using cvtColor().



### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.


### Step4
Apply the filters using cv2.filter2D() for each respective filters.



### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().



## Program:
### Developed By   :Deepika J
### Register Number:212221230016
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("doll.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")



```
ii) Using Weighted Averaging Filter
```Python

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")



```
iii) Using Gaussian Filter
```Python


gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")



```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")




```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python


kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")


```
ii) Using Laplacian Operator
```Python

laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")



```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

![img1](https://user-images.githubusercontent.com/94747031/230782922-7bbef89e-7775-4c2a-83da-6ac0971ae167.png)

ii) Using Weighted Averaging Filter

![img2](https://user-images.githubusercontent.com/94747031/230782931-28355ef8-7b24-4937-8c65-d85995641aac.png)


iii) Using Gaussian Filter

![img3](https://user-images.githubusercontent.com/94747031/230782940-cd9c341d-b937-49be-9361-0f00c4dbd70a.png)


iv) Using Median Filter

![img4](https://user-images.githubusercontent.com/94747031/230782952-0c5f93dc-5b98-42e5-bd27-8cca69955c85.png)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![img5](https://user-images.githubusercontent.com/94747031/230782966-5dcae3f5-caf6-4cfb-bbc4-41ec47a44bbb.png)


ii) Using Laplacian Operator
![img6](https://user-images.githubusercontent.com/94747031/230782979-10368a13-1698-4a0a-80a0-3881df391de3.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
