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

Averaging filter
Weighted Averaging Filter
Gaussian Blur
Median filter

### Step4
Apply following filters to the image for sharpening:
Laplacian kernel
Laplacian operator

### Step5
Apply following filters to the image for sharpening:
Laplacian kernel
Laplacian operator

## Program:
### Developed By   :Sithi Hajara I
### Register Number:212221230102

#### Importing libraries:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### 1. Smoothing Filters

i) Using Averaging Filter
```
img1=cv2.imread('dore.jpeg')
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
![Screenshot 2023-04-09 222659](https://user-images.githubusercontent.com/94219582/230786813-f2757f3c-4db5-4282-8f8d-a277621b52b7.png)

ii) Using Weighted Averaging Filter
![Screenshot 2023-04-09 222750](https://user-images.githubusercontent.com/94219582/230786854-170af949-27b6-4af2-bc4e-81bc1a50a3f1.png)

iii) Using Gaussian Filter
![image](https://user-images.githubusercontent.com/94219582/230786906-dd3a3d8e-1133-43b0-b3db-70f111c524cc.png)

iv) Using Median Filter
![Screenshot 2023-04-09 222913](https://user-images.githubusercontent.com/94219582/230786930-cf80cddc-e0bb-4f1c-8e65-07b584ee09d4.png)

### 2. Sharpening Filters
i) Using Laplacian Kernal
![Screenshot 2023-04-09 222951](https://user-images.githubusercontent.com/94219582/230787122-7a7788c4-3036-4f64-88ce-f5521a0126e0.png)


ii) Using Laplacian Operator

![Screenshot 2023-04-09 223148](https://user-images.githubusercontent.com/94219582/230787136-fda87670-c805-4681-a6e1-427835837c69.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
