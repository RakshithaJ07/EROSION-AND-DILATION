# Implementation-of-Erosion-and-Dilation

## Aim:

To implement Erosion and Dilation using Python and OpenCV.

## Software Required:

1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step1:

Import the necessary pacakages

### Step2:

Create the text using cv2.putText

#### Step3:

Create a structuring element for morphological operations (e.g., a cross-shaped kernel).

#### Step4:

Apply erosion to the image using the defined structuring element to reduce the size of white regions.

#### Step5:

Apply dilation to the original image using the same structuring element to increase the size of white regions.

#### Step6:

Display the output.

## Program :
##### Developed by : Rakshitha J

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")

# Create the text using cv2.putText
text = "RAKSHITHA"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (20, 200), font, 3, (255, 255, 255), 7)

# Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Erode the image
eroded_image = cv2.erode(image, kernel, iterations=1)

# Dilate the image
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)

# Plot the original, eroded, and dilated images using Matplotlib
plt.figure(figsize=(10, 6))
plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
plt.tight_layout()
plt.show()

plt.figure(figsize=(10, 6))
plt.subplot(1, 3, 2)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")
plt.tight_layout()
plt.show()

plt.figure(figsize=(10, 6))
plt.subplot(1, 3, 3)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")
plt.tight_layout()
plt.show()
```

## Output:

### Original image:

![download](https://github.com/user-attachments/assets/7dac5ccf-3f1b-4ffe-b258-7e6ee45915b0)

### Eroded image:

![download](https://github.com/user-attachments/assets/a0c78691-ff0a-42e5-be6d-4e097a6ab2e7)

### Dilated image:

![download](https://github.com/user-attachments/assets/70a1dbf4-1d29-487d-8598-6565c5054917)

## Result :

Thus , the generated text image is eroded and dilated using python and OpenCV.








