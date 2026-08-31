# Exp-10--Record-IMPLEMENTATION-OF-OPENING-AND-CLOSING
# Nmae : Selvaganesh B
# Reg.No : 212224230258
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

## Step 1: 
Import the required libraries cv2, numpy, and matplotlib.

## Step 2: 
Create a black image using NumPy with a suitable size.

## Step 3:
Create the text "KANIGAVEL" on the image using cv2.putText().

## Step 4:
Display the original text image.

## Step 5:
Add small white noise to the image to demonstrate the effect of Opening.

## Step 6:
Create a structuring element (kernel) using a 7 × 7 matrix.

## Step 7:
Perform the Opening operation using erosion followed by dilation to remove small noise.

## Step 8: Perform the Closing operation using dilation followed by erosion to fill small gaps in the text.

## Step 9:
Display the Original Text, Text with Noise, Opening, and Closing results using Matplotlib.

## Step 10: 
Compare the output images and observe the effect of Opening and Closing
 
## Program:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt


img = np.zeros((300, 800), dtype=np.uint8)


cv2.putText(img, "Raviprasath", (200, 200),cv2.FONT_HERSHEY_SIMPLEX, 2, 255, 5)

noise = np.random.randint(0, 2, (300, 800), dtype=np.uint8) * 255
noise = cv2.morphologyEx(noise, cv2.MORPH_OPEN,np.ones((2, 2), np.uint8))

img_with_noise = cv2.bitwise_or(img, noise)


kernel = np.ones((7, 7), np.uint8)


opening = cv2.morphologyEx(img_with_noise, cv2.MORPH_OPEN, kernel)


closing = cv2.morphologyEx(img_with_noise, cv2.MORPH_CLOSE, kernel)


plt.figure(figsize=(16, 8))


plt.subplot(1, 4, 1)
plt.imshow(img, cmap='gray')
plt.title("Original Text")
plt.axis("off")

plt.subplot(1, 4, 2)
plt.imshow(img_with_noise, cmap='gray')
plt.title("Text + Noise")
plt.axis("off")


plt.subplot(1, 4, 3)
plt.imshow(opening, cmap='gray')
plt.title("Opening")
plt.axis("off")


plt.subplot(1, 4, 4)
plt.imshow(closing, cmap='gray')
plt.title("Closing")
plt.axis("off")

plt.tight_layout()
plt.show()
```
## Output:

<img width="1589" height="183" alt="download" src="https://github.com/user-attachments/assets/4f6bdce2-9d4e-4ab3-99f0-34033949c4af" />

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
