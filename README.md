# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules and read the image.

### Step2
Perform linear filtering operation.

### Step3
Apply following filters to the image for smoothing:

1.Averaging filter
2.Weighted Averaging Filter
3.Gaussian Blur
4.Median filter

### Step4
Apply following filters to the image for sharpening:
1.Laplacian kernel
2.Laplacian operator 

### Step5
Apply following filters to the image for sharpening: Laplacian kernel Laplacian operator

## Program:
### Developed By   :Vishranthi A
### Register Number:212221230124

### Importing libraries:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### 1. Smoothing Filters

i) Using Averaging Filter
```
img1=cv2.imread('lee.jpg')
img2=cv2.cvtColor(img1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121
img3=cv2.filter2D(img2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(img2)
plt.title('Original')
plt.axis('Off')
plt.subplot(1,2,2)
plt.imshow(img3)
plt.title("Filtered")
plt.axis("Off")

```
ii) Using Weighted Averaging Filter
```
kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
img3=cv2.filter2D(img2,-1,kernel2)
plt.imshow(img3)
plt.title("Weighted Averaging Filter")
plt.axis("Off")

```
iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(src=img2,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blurring")
plt.axis("Off")

```

iv) Using Median Filter
```
median=cv2.medianBlur(src=img2,ksize=11)
plt.imshow(median)
plt.title("Median Blurring")
plt.axis("Off")

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3=cv2.filter2D(img2,-1,kernel3)
plt.imshow(img3)
plt.title("Laplacian kernel")
plt.axis("Off")

```
ii) Using Laplacian Operator
```
new_img=cv2.Laplacian(img2,cv2.CV_64F)
plt.imshow(new_img)
plt.title("Laplacian Operator")
plt.axis("Off")

```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![image](https://user-images.githubusercontent.com/93427278/230788354-83b42ada-e68c-456d-b76e-ab79b3623b51.png)

ii) Using Weighted Averaging Filter

![image](https://user-images.githubusercontent.com/93427278/230788530-75a0ab0d-51f3-42ed-932a-3de133841fc9.png)

iii) Using Gaussian Filter

![image](https://user-images.githubusercontent.com/93427278/230788548-4c3d50ec-d19d-45f5-85e8-8d793ca21dea.png)

iv) Using Median Filter

![image](https://user-images.githubusercontent.com/93427278/230788570-1cae3d3b-4b48-4f37-bff7-d10be561633d.png)

### 2. Sharpening Filters

i) Using Laplacian Kernal

![image](https://user-images.githubusercontent.com/93427278/230788595-39f3556a-b88d-408a-80bf-6e6f1d187729.png)

ii) Using Laplacian Operator

![image](https://user-images.githubusercontent.com/93427278/230788632-9506a682-c1c9-4b7d-a27f-2e9af8d1df5a.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
