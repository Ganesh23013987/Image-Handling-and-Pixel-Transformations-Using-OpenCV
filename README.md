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
- **Name:** GANESH D  
- **Register Number:** 212223240035

  ### Ex. No. 01


# Step 1: Import python necessary libraries and Read the image using CV2
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)
```

# Step 2: Print image size
```
img.shape
```

<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/ecf40f46-35e1-4254-a684-e1cacfadeb19" />

# Step 3: Convert BGR to RGB
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

# Step 4: Display original image
```
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/9d5c590d-e6f5-438e-be57-c0a192b5f05e" />


# Step 5: Draw Line
```
line_img = cv2.line(img_rgb.copy(), (0,0), (651,518), (255,0,0), 5)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/09e45233-7ed9-47b3-897e-74285d41c0e9" />

# Step 6: Draw Circle
```
circle_img = cv2.circle(img_rgb.copy(), (400,300), 150, (255,0,0), 10)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/fd3243b2-98f4-453c-bd1e-6ae30689342b" />


# Step 7: Draw Rectangle
```
rectangle_img = cv2.rectangle(img_rgb.copy(), (0,0), (651,518), (0,0,255), 10)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/fbc81b6d-9923-4729-9f67-4ddb6b1b6333" />


# Step 8: Add Text
```
text_img = cv2.putText(img_rgb.copy(), "OpenCV Drawing", (80,60),cv2.FONT_HERSHEY_SIMPLEX, 1.2, (0,255,0), 3)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/8b1a0b4b-e1a6-4571-adf0-2a3ac6d7a76e" />

# Step 9: Load the image and convert to RGB image
```
image = cv2.imread('eagle.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/87988390-4157-4ce4-9d69-a4d5f0baca98" />

# Step 10: Convert RGB to HSV
```
image_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/228fac8c-4a7d-4755-aaba-921d40123424" />


# Step 11: Convert RGB to Gray
```
image_gray = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/42fcfb4c-614d-45ec-90db-e959a2158bfd" />


# Step 12: Convert RGB to YCrCb
```
image_ycrcb = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/46274cef-006f-4fbc-93cc-3c79465c92dd" />

# Step 13: Convert HSV back to RGB
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/7a15b74f-0062-45fd-a122-bcde90dadf63" />


# Step 14: White Block
```
img[180:480,220:520] = [255,255,255]

plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/9d70554b-3491-40d9-9898-d024f6c5ce6a" />


# Step 15: Resize
```
image = cv2.imread('eagle.jpg')
resize = cv2.resize(image, (384,300))

plt.imshow(cv2.cvtColor(resize, cv2.COLOR_BGR2RGB))
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/f650e011-6033-4628-9fa3-f0d7140a73ca" />


# Step 16: Crop
```
crop = image[120:420,150:500]

plt.imshow(cv2.cvtColor(crop, cv2.COLOR_BGR2RGB))
plt.title("Cropped Eagle")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/fc0802a3-a997-479c-87c9-2881c48e0bdc" />


# Step 17: Horizontal Flip
```
flip_h = cv2.flip(image,1)

plt.imshow(cv2.cvtColor(flip_h, cv2.COLOR_BGR2RGB))
plt.title("Horizontal Flip")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/dfda37d9-7e50-4abc-ae01-622f02217423" />


# Step 18: Vertical Flip
```
flip_v = cv2.flip(image,0)

plt.imshow(cv2.cvtColor(flip_v, cv2.COLOR_BGR2RGB))
plt.title("Vertical Flip")
plt.axis("off")
plt.show()
```

<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/300adf4a-ad32-4ed9-9ab8-2ff207abb29d" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

