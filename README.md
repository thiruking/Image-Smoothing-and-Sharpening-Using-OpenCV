# Image Smoothing and Sharpening Using OpenCV

## Aim
To apply smoothing and sharpening filters using OpenCV and display the output images.

---

## Software Used
- Python 3.x
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook / VS Code

---

## Algorithm

### Step 1
Import required libraries.

### Step 2
Read the input image.

### Step 3
Convert image from BGR to RGB format.

### Step 4
Apply Averaging Filter.

### Step 5
Apply Weighted Averaging Filter.

### Step 6
Apply Gaussian Filter.

### Step 7
Apply Median Filter.

### Step 8
Apply Laplacian Sharpening Filter.

### Step 9
Apply Laplacian Operator for edge detection.

### Step 10
Display all output images using subplot.

---

## PROGRAM :

```PY
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread("d1.webp")

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

avg_filter = cv2.blur(img_rgb, (5,5))

kernel = np.array([[1,2,1],
                   [2,4,2],
                   [1,2,1]]) / 16

weighted_avg = cv2.filter2D(img_rgb, -1, kernel)

gaussian_filter = cv2.GaussianBlur(img_rgb, (5,5), 0)

median_filter = cv2.medianBlur(img_rgb, 5)

laplacian_kernel = np.array([[0,-1,0],
                             [-1,5,-1],
                             [0,-1,0]])

laplacian_sharp = cv2.filter2D(img_rgb, -1, laplacian_kernel)

gray = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2GRAY)

laplacian_operator = cv2.Laplacian(gray, cv2.CV_64F)

laplacian_operator = np.uint8(np.absolute(laplacian_operator))

plt.figure(figsize=(15,12))

plt.subplot(3,3,1)
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(3,3,2)
plt.imshow(avg_filter)
plt.title("Averaging Filter")
plt.axis("off")

plt.subplot(3,3,3)
plt.imshow(weighted_avg)
plt.title("Weighted Averaging")
plt.axis("off")

plt.subplot(3,3,4)
plt.imshow(gaussian_filter)
plt.title("Gaussian Filter")
plt.axis("off")

plt.subplot(3,3,5)
plt.imshow(median_filter)
plt.title("Median Filter")
plt.axis("off")

plt.subplot(3,3,6)
plt.imshow(laplacian_sharp)
plt.title("Laplacian Sharpening")
plt.axis("off")

plt.subplot(3,3,7)
plt.imshow(laplacian_operator, cmap='gray')
plt.title("Laplacian Operator")
plt.axis("off")

plt.tight_layout()
plt.show()
```

## Output
- Averaging filter smooths the image
<img width="769" height="314" alt="image" src="https://github.com/user-attachments/assets/159e51fd-d5ba-4729-98ad-5556953a6f71" />

- Gaussian filter reduces noise
  <img width="621" height="261" alt="image" src="https://github.com/user-attachments/assets/7972687f-e5a0-43ac-96e4-6b2589c081c0" />

- Median filter removes salt-and-pepper noise

  <img width="621" height="261" alt="image" src="https://github.com/user-attachments/assets/33d6e97f-9f91-47ab-854b-0eb0f00faf0e" />

- Laplacian filter sharpens edges
- Laplacian operator detects edges clearly
<img width="950" height="261" alt="image" src="https://github.com/user-attachments/assets/b4e17fe6-9062-496e-862d-ca8df2b87f99" />

---

## Result
Thus, smoothing and sharpening filters are successfully implemented using OpenCV.

---

## Developed By

**Name:** ____THIRUMALAI K______

**Register No:** __212224240176____
