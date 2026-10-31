## Exp-6 : Record-EDGE-DETECTION

## NAME :UDHAYA S
## REG NO : 212225230287

## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program


```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('udhaya_.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="382" height="492" alt="image" src="https://github.com/user-attachments/assets/e1d847e7-ab41-458e-8971-ca4d010e8e26" />


### 1. Sobel Edge Detector

<img width="383" height="487" alt="image" src="https://github.com/user-attachments/assets/04fc37ec-8eea-486d-8465-4885dc70ec80" />



### 2. Laplacian Edge Detector

<img width="395" height="495" alt="image" src="https://github.com/user-attachments/assets/6d23e816-016d-4c55-b073-613505821dfc" />


### 3. Canny Edge Detector

<img width="343" height="460" alt="image" src="https://github.com/user-attachments/assets/959bbb44-9d52-416a-a63c-c546d9751c18" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
