# EX.No: 6-EDGE DETECTION
## Name: DHANAPPRIYA S
## Register No: 212224230056

# **Aim**

To perform edge detection on a given image using Sobel, Laplacian, and Canny edge detection techniques in OpenCV.

---

# **Procedure**

1. **Load and Convert Image:** Read the input image using OpenCV (`cv2.imread`) and convert it from BGR to grayscale (`cv2.cvtColor`).
2. **Sobel Edge Detection:** Compute the gradient along the X and Y directions using `cv2.Sobel()`, and combine them using `cv2.magnitude()` to highlight horizontal and vertical edges.
3. **Laplacian Edge Detection:** Apply the Laplacian operator (`cv2.Laplacian()`) to detect regions with rapid intensity changes in all directions.
4. **Canny Edge Detection:** Apply the Canny algorithm (`cv2.Canny()`) with specified threshold values (e.g., 50 and 150) to extract clear, thin edges.
5. **Display Results:** Plot and visualize the original image along with the detected edge outputs using Matplotlib (`plt.imshow`).Here is the simple, short aim and procedure based on your Jupyter Notebook experiment on **Edge Detection**:

# Code:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('photo.jpg')  # Replace with your image path
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
# Output:
<img width="908" height="570" alt="image" src="https://github.com/user-attachments/assets/c3202ba7-4526-4d99-bc8b-99f5c52f45ce" />
<img width="887" height="570" alt="image" src="https://github.com/user-attachments/assets/a8da75a9-1315-496f-9a1e-8a082a1d6fdf" />
<img width="875" height="557" alt="image" src="https://github.com/user-attachments/assets/c133616c-53b4-44f7-9445-41eddbf31c2b" />
<img width="893" height="562" alt="image" src="https://github.com/user-attachments/assets/5cd0aa33-b4a5-429f-8555-0822b2cb7935" />

# Result:
Thus to  perform edge detection on a given image using Sobel, Laplacian, and Canny edge detection techniques in OpenCV was verified successfully.
