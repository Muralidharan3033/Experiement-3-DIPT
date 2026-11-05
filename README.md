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

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

plt.figure(figsize=(20, 10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.figure(figsize=(15, 4))
plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

### Developed By:
**Name:** MURALIDHARAN M

### Register No:
212223040120  

---

##  Output
### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast

<img width="1390" height="692" alt="image" src="https://github.com/user-attachments/assets/908bdb82-ea7f-404e-b28a-4f257f8a2290" />
<img width="1372" height="736" alt="image" src="https://github.com/user-attachments/assets/a5c2fc3e-6a36-44d2-b06d-30d3d939653e" />
<img width="1437" height="760" alt="image" src="https://github.com/user-attachments/assets/cfeb1d54-c36a-4c84-aaea-43163f2a9bcc" />
<img width="1472" height="682" alt="image" src="https://github.com/user-attachments/assets/349ec345-c8c7-488f-9635-f46f074142a2" />

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution
  
<img width="1370" height="587" alt="image" src="https://github.com/user-attachments/assets/74438c27-18d5-42f5-95cc-fa55bdb5a93d" />
<img width="1256" height="638" alt="image" src="https://github.com/user-attachments/assets/0a711e5b-3534-4230-956c-528cdc71f37c" />
<img width="1842" height="542" alt="image" src="https://github.com/user-attachments/assets/14f25fe8-23f1-40d1-8c73-7eb14e3025fe" />
<img width="1856" height="545" alt="image" src="https://github.com/user-attachments/assets/0912228e-2b8c-4fd5-8021-ab934231095b" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
