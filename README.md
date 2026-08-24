# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** [Your Name Here]  
- **Register Number:** [Your Register Number Here]

  ### Ex. No. 01

code:
```
python
import cv2
import matplotlib.pyplot as plt

# --------------------------------------------------
# 1. Read Image
# --------------------------------------------------
image = cv2.imread('saveetha.jpg')

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

print("Original Image Shape:", image.shape)


# --------------------------------------------------
# 2. Display Original Image
# --------------------------------------------------
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 3. Draw Line
# --------------------------------------------------
line_img = image_rgb.copy()

cv2.line(line_img, (0, 0), (768, 600), (255, 0, 0), 2)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 4. Draw Circle
# --------------------------------------------------
circle_img = image_rgb.copy()

cv2.circle(circle_img, (400, 300), 150, (255, 0, 0), 10)

plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 5. Draw Rectangle
# --------------------------------------------------
rectangle_img = image_rgb.copy()

cv2.rectangle(
    rectangle_img,
    (0, 0),
    (768, 600),
    (0, 0, 255),
    10
)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 6. Add Text
# --------------------------------------------------
text_img = image_rgb.copy()

cv2.putText(
    text_img,
    "OpenCV Drawing",
    (10, 30),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    (255, 255, 255),
    10
)

plt.imshow(text_img)
plt.title("Image with Text")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 7. Convert RGB to HSV
# --------------------------------------------------
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 8. Convert RGB to Grayscale
# --------------------------------------------------
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 9. Convert RGB to YCrCb
# --------------------------------------------------
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 10. Convert HSV back to RGB
# --------------------------------------------------
image_hsv_to_rgb = cv2.cvtColor(
    image_hsv,
    cv2.COLOR_HSV2RGB
)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 11. Modify 300x300 Block to White
# --------------------------------------------------
white_block = image.copy()

white_block[200:500, 200:500] = [255, 255, 255]

white_block_rgb = cv2.cvtColor(
    white_block,
    cv2.COLOR_BGR2RGB
)

plt.imshow(white_block_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 12. Resize Image to Half
# --------------------------------------------------
resized_image = cv2.resize(
    image,
    (image.shape[1] // 2, image.shape[0] // 2)
)

resized_image_rgb = cv2.cvtColor(
    resized_image,
    cv2.COLOR_BGR2RGB
)

print("Resized Image Shape:", resized_image.shape)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 13. Crop 300x300 Region
# --------------------------------------------------
roi = image[50:350, 50:350]

roi_rgb = cv2.cvtColor(
    roi,
    cv2.COLOR_BGR2RGB
)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 14. Flip Horizontally
# --------------------------------------------------
flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(
    flipped_horizontally,
    cv2.COLOR_BGR2RGB
)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()


# --------------------------------------------------
# 15. Flip Vertically
# --------------------------------------------------
flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(
    flipped_vertically,
    cv2.COLOR_BGR2RGB
)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```


## Output:
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/e07ff435-1add-4124-af57-493ff046a4d2" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/bbba7897-dd5a-44ad-bc61-9ce8889a984a" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/bf5b0323-f02d-4357-9051-5e937fbdd3e5" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/d24f8e32-c793-4f37-938e-8138dee82eb9" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/01789d83-9b88-45ae-bf06-ba362af4601d" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/f6565079-5ab9-4c72-9eee-3a9dc0921b2f" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/c1eeb34e-4095-4d01-992c-1183353ab2f2" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/a64bcc92-8e49-4953-9eb7-3b509cf4a567" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/173fa5e4-dae6-4647-976d-8da0558b89b0" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/428066f1-aa8c-4472-a8d0-07fbbf460aa4" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/d0282938-a1e3-45d8-bef3-8548c6660a7f" />
<img width="438" height="410" alt="download" src="https://github.com/user-attachments/assets/d8b8a04a-2036-4ae9-81b3-372897f5475c" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

