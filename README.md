# Histogram Equalization Using OpenCV (Grayscale & Color Images)

## Name : Ramnithish R
## Reg No : 212224230219
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
Read the image `12.jpg` in grayscale format.

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
## 1. Import the required libraries and read the grayscale image.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('12.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
## 2. Plot the histogram of the grayscale image.
```
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```
## 3. Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
```
## 4. Display the histogram of the equalized image.
```
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
## 5. Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
## 6. Read the image in color mode and convert to HSV.
```
img = cv2.imread('gta.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
## 7. Apply histogram equalization to the V channel.
```
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
## 8. Convert the enhanced HSV image back to BGR.
```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
## 9. Display the original and equalized color images.
```
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```
## 10. Display the original and equalized images along with their histograms.
```
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

##  Output

<img width="1357" height="558" alt="image" src="https://github.com/user-attachments/assets/47985460-f656-47c2-95c4-b5276d6fc7f5" /><br>
<img width="1391" height="558" alt="image" src="https://github.com/user-attachments/assets/6d824b99-3e76-4f09-88af-94ba0915fda7" /><br>
<img width="1339" height="540" alt="image" src="https://github.com/user-attachments/assets/2c2849a5-6fe1-42ee-991d-13f5c2779648" /><br>
<img width="1191" height="548" alt="image" src="https://github.com/user-attachments/assets/5977b99c-a9b9-4af0-81dc-037346504bda" /><br>
<img width="1345" height="553" alt="image" src="https://github.com/user-attachments/assets/a952889b-f44d-43ab-a092-03bc0cb0e6a8" /><br>
<img width="1353" height="555" alt="image" src="https://github.com/user-attachments/assets/f2ca4b23-f697-491f-897a-ff1253b57def" /><br>
<img width="1372" height="508" alt="image" src="https://github.com/user-attachments/assets/2500622c-6e97-4417-99b6-454490fb0bf5" /><br>
<img width="1360" height="405" alt="image" src="https://github.com/user-attachments/assets/3870dc12-e4c5-4484-961a-f156557ec0f9" />


## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
