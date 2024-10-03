# EXP.4-IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.
### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.
### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```
Developed By: KISHORE.B
Register Number: 212222110020
```
# LOAD THE IMAGE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('BIRD.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/49b43b9c-5155-4271-8edf-f18da13d5380)

# 1. Translation
```
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
## OUTPUT
![image](https://github.com/user-attachments/assets/df7a78c5-bf28-467b-a696-ee8cdc66faca)

# 2. Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/13f4dbb9-e697-493b-a1bc-9941e4ea1445)

# 3. Shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')

```
# OUTPUT:
![image](https://github.com/user-attachments/assets/8f731c54-6dc9-432e-9f84-147eec9cccae)

# 4. Reflection (Flip)
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/eaac9f1e-9ef0-4a48-9374-3f322abee6f4)

# 5. Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.tight_layout()
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/88c9e53d-7cfc-410f-b681-0e6b2684ad9b)

# 6. Cropping
```
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/97267a5e-e5e5-4aad-ae68-d7cf1070d175)






## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
