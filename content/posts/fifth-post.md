---
title: "Image Processing for OCR"
date: 2024-10-22T15:53:57-05:00
draft: false
tags: ["Python","Machine Learning","Image Processing","Image Processing OCR", "Learning notes"]
categories: ["Python"]
---
Before feeding an image to an OCR system, various image processing techniques are applied to improve text visibility and minimize noise or distortions. The basic steps are as follows:

### **1. Image Acquisition**

- This is the first step, where the image is captured from a source like a scanner, camera, or downloaded from a file. The image could be in various formats such as JPG, PNG, TIFF, etc.

### **2. Preprocessing**

The goal of preprocessing is to prepare the image to make it easier for the OCR engine to read the text. Common preprocessing steps include:

- **Grayscale Conversion**: Convert the image to grayscale to simplify the image by removing color information. OCR systems generally work best with grayscale or binary images.
    
    ```python
    gray_image = cv2.cvtColor(input_img, cv2.COLOR_BGR2GRAY)
    ```
    
- **Noise Removal**: Remove unwanted artifacts and distortions (such as speckles, background noise) that can affect OCR accuracy. This can be done using techniques like:
    - **Median Filtering** to remove salt-and-pepper noise.
    - **Gaussian Smoothing** to reduce image noise.
    
    ```python
    blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)
    ```
    
- **Thresholding**: Convert the grayscale image to a binary image, where text appears in white and the background appears in black (or vice versa). This is typically done using methods like Otsu's thresholding or adaptive thresholding.
    
    ```python
    python
    _, binary_image = cv2.threshold(gray_image, 128, 255, cv2.THRESH_BINARY)
    ```
    
- **Dilation and Erosion**: These morphological operations help in closing gaps between characters and lines, making text more distinct.
    - **Erosion**: Removes small white noise or gaps.
    - **Dilation**: Helps in making text thicker and closing small holes inside objects (characters).
    
    ```python
    kernel = np.ones((2, 2), np.uint8)
    dilated_image = cv2.dilate(binary_image, kernel, iterations=1)
    ```
    
- **Skew Correction**: Ensures that text lines are properly aligned by correcting any tilt in the image.
    - **Hough Line Transform** or other deskewing algorithms can detect the skew angle and rotate the image.
    
    ```python
    (h, w) = gray_image.shape[:2]
    rotated = cv2.getRotationMatrix2D((w / 2, h / 2), angle, 1.0)
    deskewed_image = cv2.warpAffine(binary_image, rotated, (w, h))
    ```
    

### **3. Text Region Detection (Optional)**

- If the image contains both text and non-text regions (e.g., tables, figures), a region detection algorithm like Connected Component Analysis (CCA) or Edge Detection may be applied to isolate the areas of text.