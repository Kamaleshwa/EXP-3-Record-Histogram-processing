# EX03-Histogram-of-an-images

## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program

#### Name: KAMALESHWAR KV
#### Reg.No: 212223240063

### 1.Import Python necessary libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### 2.Histogram Equalization for Grayscale Images

```
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/1afd9591-7400-4647-931f-666e7f320d33" />

```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/1429f354-1aed-440e-8230-febcaf09fed0" />

```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/e2855d97-29b2-4b1a-a7e3-9fd81d46937b" />

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/71ad0ad1-7883-479c-9d77-bea5ddea4c16" />

### 3.Histogram Equalization for Color Images
```
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/60de07f0-8687-4eda-be71-6576fc37d4c3" />

```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/56dac206-46a0-4628-8388-24aa1231260a" />

```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
<img width="1580" height="461" alt="image" src="https://github.com/user-attachments/assets/ead75d68-fb58-431c-ac09-7a3ed8a68a04" />

```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
<img width="1571" height="473" alt="image" src="https://github.com/user-attachments/assets/c749d1cb-bf30-4e26-ad82-154d94f0bb52" />

## Result:
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
