# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```
# Developed By: SUDHIR KUMAR. R
# Register Number: 212223230221
```

```python
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg") 
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Color Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

```python
import cv2
import matplotlib.pyplot as plt

gray_image = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg")

gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
color_hist = cv2.calcHist([color_image], [0], None, [256], [0, 256])

plt.figure(figsize=(12, 6))

plt.subplot(1, 2, 1)
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='black')

plt.subplot(1, 2, 2)
plt.title("Color Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(color_hist, color='blue')

plt.tight_layout()
plt.show()
```

```python
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\dig-img-process\gray-fie.jpeg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread(r"C:\Users\admin\dig-img-process\fie.jpg")
resized_gray_image = cv2.resize(gray_image, (500, 400))
equalized_image = cv2.equalizeHist(gray_image)
cv2.imshow("Original Grayscale Image", gray_image)
cv2.waitKey(0)

cv2.imshow("Resized Grayscale Image", resized_gray_image)
cv2.waitKey(0)
cv2.imshow("Equalized Grayscale Image", equalized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

plt.figure()

plt.subplot(1, 2, 1)
plt.title("Original Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(gray_hist)

plt.subplot(1, 2, 2)
plt.title("Equalized Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
equalized_hist = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.plot(equalized_hist)

plt.tight_layout()
plt.show()


```
## Output:
### Input Grayscale Image and Color Image

![Screenshot 2024-09-30 151541](https://github.com/user-attachments/assets/61192b72-2dbc-473f-8fe6-9b056136dc75)

### Histogram of Grayscale Image and any channel of Color Image

![Screenshot 2024-09-30 151848](https://github.com/user-attachments/assets/d824b121-08e4-4f3f-a3e4-efffc4f21369)

### Histogram Equalization of Grayscale Image.

![Screenshot 2024-09-30 152026](https://github.com/user-attachments/assets/43062757-1eeb-4b85-9bc2-fb6ddb9ca116)

![Screenshot 2024-09-30 152047](https://github.com/user-attachments/assets/546aa194-f71b-4ecb-81cf-691381834bfd)

![Screenshot 2024-09-30 152110](https://github.com/user-attachments/assets/c29f2a46-f861-444e-9a3c-571bc0639f16)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
