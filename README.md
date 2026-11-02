# Histogram-of-an-images
# Name: VARSHINI K M 
# Reg no: 212225240179

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

<img width="238" height="280" alt="image" src="https://github.com/user-attachments/assets/16340033-1272-4d9b-b05d-c4a30e2cae60" />

### Input Grayscale Image Range
<img width="372" height="281" alt="image" src="https://github.com/user-attachments/assets/99107d6a-628f-4f37-9050-f9c1211accdd" />

### Input Grayscale Image Equalized Histogram
<img width="393" height="281" alt="image" src="https://github.com/user-attachments/assets/141e8dbc-cfcf-4598-b5ef-a3718e6cf4a2" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="245" height="287" alt="image" src="https://github.com/user-attachments/assets/9b9b24a4-199a-4cda-a93b-3ac06a0a7e95" />

### Equalized Image

<img width="240" height="273" alt="image" src="https://github.com/user-attachments/assets/ac1458f7-63a5-4da0-a3db-0c908dc1d0b3" />

### Equalized Histogram
<img width="360" height="277" alt="image" src="https://github.com/user-attachments/assets/b7b5c072-a238-4f7d-a21b-581659177f58" />

### Final Output of Original Image and Equalized 
<img width="678" height="241" alt="image" src="https://github.com/user-attachments/assets/90b8e7ce-e8b9-4f2e-be23-ce34a4e5ce13" />



### Final Output of Original Image and its Histogram Equalized
<img width="676" height="216" alt="image" src="https://github.com/user-attachments/assets/b6ba873e-bcc6-4763-9caf-51761e0348f3" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
