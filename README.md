# VR_Assignment1_Trupti_Khodwe_IMT2022007

## Visual Recognition Assignment 1

This repository contains solutions for the VR assignment 1, including coin detection and segmentation, as well as image stitching for panorama creation.

## Table of Contents
- [Installation & Dependencies](#installation--dependencies)
- [How to Run](#how-to-run)
- [Part 1: Coin Detection and Segmentation](#part-1-coin-detection-and-segmentation)
  - [a. Coin Detection](#a-coin-detection)
  - [b. Coin Segmentation](#b-coin-segmentation)
  - [c. Coin Counting](#c-coin-counting)
- [Part 2: Image Stitching for Panorama](#part-2-image-stitching-for-panorama)
- [Results & Observations](#results--observations)
- [Dataset](#dataset)

---

## Installation & Dependencies
Ensure you have the required dependencies installed before running the scripts.

```bash
pip install opencv-python numpy matplotlib
```

---

## How to Run
### Part 1: Coin Detection, Segmentation and count of coins

- The code files and the images needed for code execution are in the Part 1 directory, so ensure you are in that directory before running the code files.  
- 1_a.ipynb file has the code for Coin Detection. Since, it is an .ipynb file, for each cell just do "shift + enter", that cell will be executed. This way, execute all the cells. 
- 1_b.ipynb file has the code for Coin Segmentation. Since, it is an .ipynb file, for each cell just do "shift + enter", that cell will be executed. This way, execute all the cells. 
- 1_c.ipynb file has the code for counting the number of coins in the image. Since, it is an .ipynb file, for each cell just do "shift + enter", that cell will be executed. This way, execute all the cells. 

### Part 2: Image Stitching for Panorama

- The code files and the images needed for code execution are in the Part 2 directory, so ensure you are in that directory before running the code files.  
- 2.ipynb file has the code for creating a Panorama by stiching images. Since, it is an .ipynb file, for each cell just do "shift + enter", that cell will be executed. This way, execute all the cells.

---

## Part 1: Coin Detection and Segmentation

### a. Coin Detection
- Loaded the image from the given path.
- Converted the image to grayscale.
- Applied **Gaussian Blur** to smooth the image and remove noise.
- Used **Adaptive Thresholding** to separate coins from the background.
- **Detected contours** representing coin edges.
- Filtered small contours based on area to remove unwanted noise.
- Outlined detected coins on the original image using contours.
- Converted the image to RGB format for proper display in Matplotlib.
- Displayed the final image with detected coins.

**Detected Coins:**  
![Detected Coins](Part%201/1_a.png)

---

### b. Coin Segmentation
- Loaded the image from the given path.
- Converted the image to grayscale.
- Applied Gaussian Blur to smooth the image and remove noise.
- Used Otsu’s Thresholding to convert the image into a binary mask.
- Detected contours representing coin edges.
- Filtered small contours based on area to remove unwanted detections.
- Sorted the contours in descending order by area.
- Removed nested contours to ensure only full coins were segmented.
- Extracted each segmented coin using bounding boxes.
- Displayed each segmented coin using Matplotlib.

**Segmented Coins:**  
![Segmented Coins](Part%201/1_b.png)

---

### c. Coin Counting
- Loaded the image from the given path.
- Converted the image from BGR to RGB for proper visualization.
- Displayed the original image.
- Converted the image to grayscale.
- Applied Gaussian Blur to remove noise and smooth the image.
- Displayed the blurred grayscale image.
- Used Otsu’s Thresholding to create a binary mask.
- Displayed the thresholded image.
- Detected contours representing coin edges.
- Filtered small contours based on area to remove unwanted detections.
- Removed nested contours to ensure only full coins were counted.
- Counted the number of detected coins and displayed the count.
- Outlined detected coins on the original image.
- Converted the result image to RGB for proper visualization.
- Displayed the final image with detected coin count.

**Total Coins Counted:**  
![Total Coins Counted](Part%201/1_c.png)

---

## Part 2: Image Stitching for Panorama
- Used **ORB (Oriented FAST and Rotated BRIEF)** to detect key points in images.
- Matched key points between overlapping images using **BFMatcher**.
- Applied **Homography Transformation** to warp images and align them.
- Stitched multiple images into a single panoramic view.
- Cropped the black areas to improve the final output

**Detected Keypoints:**
![Keypoints](Part%202/Final%20Output%20Images/keypoints.png)

**Stitched Panorama:**  
![Stitched Panorama](Part%202/Final%20Output%20Images/Final_Panorama.png)

---

## Results & Observations
1. **Coin Detection & Counting**:
   - Successfully detected coins.
   - Adaptive thresholding combined with contour filtering helped eliminate noise and inner contours (such as the inner ring of ₹10 coins), leading to more accurate coin counting.

2. **Image Stitching**:
   - ORB feature detection worked well for matching overlapping regions.
   - Cropping the stitched image improved the final output quality.
   - Seams occuring while stiching second and third image.

---

## Dataset
- Part 2/ Final Output Images directory contains the final panorama which got generated and the keypoints which were detected.
- Part 1/ 1_a.png has the image for coin detection.
- Part 1/1_b.png has the image for coin segmentation.
- Part 1/1_c.png has the image that counts the total number of coins.
- All images used in this assignment are stored in the respective directories.

---
