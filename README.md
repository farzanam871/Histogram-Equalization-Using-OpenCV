# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---
## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---


### Developed By:
**Name:** Farzana M 

### Register No: 212225040087

---
## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('shinchan.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
```
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```
img = cv2.imread('shinchan.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
```
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```


##  Output:
**ORGINAL IMAGE:**
<img width="775" height="543" alt="Screenshot 2026-10-27 090151" src="https://github.com/user-attachments/assets/4e487370-2bd5-453a-9447-002e2295f98c" />

<img width="741" height="591" alt="Screenshot 2026-10-27 091133" src="https://github.com/user-attachments/assets/3e6c7ce6-26d2-4fad-afe3-39a2f209d398" />

**Equalised Histogram:**

<img width="747" height="557" alt="Screenshot 2026-10-27 091240" src="https://github.com/user-attachments/assets/aae4e927-77f4-4150-ae34-c27f0256276c" />

<img width="797" height="541" alt="Screenshot 2026-10-27 090202" src="https://github.com/user-attachments/assets/33a9ce45-bc91-4be7-99d8-de7d99180320" />

**Histogram of any channel of Color Image:**

<img width="1382" height="520" alt="Screenshot 2026-10-27 090305" src="https://github.com/user-attachments/assets/e8c6158f-f21e-4080-8082-bb6003461f50" />

**Histogram Equalization of Color Image:**

<img width="1390" height="563" alt="Screenshot 2026-10-27 090312" src="https://github.com/user-attachments/assets/157d83fb-8975-41f4-96ef-be809b07a170" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
