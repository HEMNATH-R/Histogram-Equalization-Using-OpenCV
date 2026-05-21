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

### Developed By: HEMNATH R  

### Register No: 212224240057

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()


```



---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

<img width="750" height="500" alt="image" src="https://github.com/user-attachments/assets/a6f946c4-eeef-4d2a-9534-5f97a1372971" />


- Histogram of original grayscale image is plotted

<img width="794" height="545" alt="image" src="https://github.com/user-attachments/assets/6626fdeb-d99d-4c47-922b-bc825241a149" />

 
- Enhanced image after histogram equalization is displayed

<img width="847" height="540" alt="image" src="https://github.com/user-attachments/assets/f7732785-c4ee-4af1-a9a1-bbb9626da494" />

- Histogram of enhanced grayscale image shows improved contrast  

<img width="789" height="500" alt="image" src="https://github.com/user-attachments/assets/cbcbcde9-6aec-4ef7-99f0-14514119dd19" />


### Color Image Histogram Equalization

- Original color image is displayed

<img width="847" height="498" alt="image" src="https://github.com/user-attachments/assets/4747af01-d4be-4404-872d-0f2498f20c69" />

- Histogram of B, G, R channels is plotted

<img width="832" height="537" alt="image" src="https://github.com/user-attachments/assets/575d8f15-e626-4635-b196-bd1bff4ad206" />

- Enhanced image after HSV-based equalization is displayed

<img width="1374" height="403" alt="image" src="https://github.com/user-attachments/assets/921ecd87-6df3-4ca6-aec6-3d0a50a9d5bb" />


- Histogram of enhanced image shows better intensity distribution  

<img width="1374" height="410" alt="image" src="https://github.com/user-attachments/assets/5b2edf25-01ec-4665-80da-9c3a4c6d3f23" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
