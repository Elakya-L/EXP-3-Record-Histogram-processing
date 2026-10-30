# Histogram-of-an-images
# Name: Elakya L
# Reg no: 212225230066

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="173" height="203" alt="image" src="https://github.com/user-attachments/assets/dea59f5f-260e-4c5b-ac7a-bfc49bafb19e" />

### Input Grayscale Image Range
<img width="320" height="200" alt="image" src="https://github.com/user-attachments/assets/6bfae901-c2f3-41bd-9a34-8bc17cbd14d5" />

### Input Grayscale Image Equalized Histogram
<img width="341" height="199" alt="image" src="https://github.com/user-attachments/assets/a63bafc5-9ff9-48c6-bf21-c8e1e6fca6c0" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="243" height="209" alt="image" src="https://github.com/user-attachments/assets/4643204c-9946-49c1-be65-f156d1ef9269" />

### Equalized Image

<img width="208" height="199" alt="image" src="https://github.com/user-attachments/assets/4cccccf7-561a-4c65-9dd4-3335afb57b15" />

### Equalized Histogram
<img width="323" height="203" alt="image" src="https://github.com/user-attachments/assets/d7aa9019-a41c-47f5-8164-1bc6a3ec7bc7" />

### Final Output of Original Image and Equalized 
<img width="506" height="173" alt="image" src="https://github.com/user-attachments/assets/7fd4ade5-8e8d-4daa-a4f4-a29c1fc2df34" />


### Final Output of Original Image and its Histogram Equalized
<img width="494" height="146" alt="image" src="https://github.com/user-attachments/assets/51213755-4043-42c9-96f3-2af736009577" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
