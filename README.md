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
- **Name:** Tamil Pavalan M  
- **Register Number:** 212223110058

  ### Ex. No. 01

```python
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('myphoto.png', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(472, 354, 3)
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(472, 354, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(472, 354, 3)
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('myphoto.png') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('myphoto.png') 
image.shape
(472, 354, 3)
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('myphoto.png') 
image.shape
(472, 354, 3)
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('myphoto.png') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(353.5), np.float64(471.5), np.float64(-0.5))

```

## Output:
**Original Image**

<img width="407" height="515" alt="image" src="https://github.com/user-attachments/assets/be19b37c-b5e8-47d7-a791-cbb0ba412967" />

**Image with Line**

<img width="372" height="507" alt="image" src="https://github.com/user-attachments/assets/da5d69c4-6d33-483a-be2b-6778aeedd7b0" />

**Image with Circle**

<img width="367" height="506" alt="image" src="https://github.com/user-attachments/assets/cd13badb-38a1-4c62-ae2f-e609c74d3289" />

**Image with Rectangle**

<img width="370" height="507" alt="image" src="https://github.com/user-attachments/assets/796bb042-311d-48fa-9bdb-cd8ac08dccec" />

**Image with Text**

![Uploading image.png…]()


**Original RGB Image**

<img width="357" height="501" alt="image" src="https://github.com/user-attachments/assets/a9d0a2d1-5db6-48fd-9dc5-b850309c7bd4" />

**HSV Image**

<img width="370" height="502" alt="image" src="https://github.com/user-attachments/assets/d913b11a-6266-4137-998c-7f6d20da9936" />

**Grayscale Image**

<img width="352" height="502" alt="image" src="https://github.com/user-attachments/assets/0d1cf148-3592-432c-874b-775282f45cb8" />

**YCrCb Image**

<img width="363" height="500" alt="image" src="https://github.com/user-attachments/assets/995f231c-06e1-434f-bf62-93f506482abd" />

**HSV to RGB Image**

<img width="372" height="505" alt="image" src="https://github.com/user-attachments/assets/ba0ef5e4-77ec-4f43-be2e-b5c9a1761856" />

**Image with 300x300 White Block**

<img width="618" height="515" alt="image" src="https://github.com/user-attachments/assets/b26b1d10-e9db-4cec-ac15-9620ed7b2e16" />

**Resized Image (Half Size)**

<img width="446" height="515" alt="image" src="https://github.com/user-attachments/assets/fff0ed4e-f4f2-4a5e-a6d1-c46ef2f2a64b" />

**Cropped Region of Interest (ROI)**

<img width="365" height="497" alt="image" src="https://github.com/user-attachments/assets/7613bbcf-9187-4c4a-a9c4-db72bcd53bfa" />

**Flipped Horizontally**

<img width="361" height="476" alt="image" src="https://github.com/user-attachments/assets/b1204e21-3f02-42e5-b81a-a1900d782048" />

**Flipped Vertically**

<img width="357" height="490" alt="image" src="https://github.com/user-attachments/assets/32f485f8-a7e1-4ac0-95f8-de0c742b82b6" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

