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
- Used **Gaussian Blur** to smooth the image and reduce noise.
- Applied **Adaptive Thresholding** to separate coins from the background.
- Used **Contour Detection** to identify coin shapes.
- Filtered out small contours based on area to remove noise.
- Outlined detected coins using OpenCV contours.

**Detected Coins:**  
![Detected Coins](Part%201/1_a.png)

---

### b. Coin Segmentation
- Applied **region-based segmentation** to isolate individual coins.
- Used bounding boxes around detected coins.
- Removed nested contours to prevent inner details (e.g., ₹10 coin inner ring) from being mistaken as separate coins.

**Segmented Coins:**  
![Segmented Coins](Part%201/1_b.png)

---

### c. Coin Counting
- Used **Contours** to count distinct coins.
- Displayed the **total number of detected coins** on the output image.

**Total Coins Counted:**  
![Total Coins Counted](Part%201/1_c.png)

---

## Part 2: Image Stitching for Panorama
- Used **ORB (Oriented FAST and Rotated BRIEF)** to detect key points in images.
- Matched key points between overlapping images using **BFMatcher**.
- Applied **Homography Transformation** to warp images and align them.
- Stitched multiple images into a single panoramic view.
- Cropped the black areas to improve the final output

**Stitched Panorama:**  
![Stitched Panorama](Part%202/Final%20Output%20Images/Final_Panorama.png)

---

## Results & Observations
1. **Coin Detection & Counting**:
   - Successfully detected coins.
   - Adaptive thresholding worked better than simple binary thresholding.

2. **Image Stitching**:
   - ORB feature detection worked well for matching overlapping regions.
   - Cropping the stitched image improved the final output quality.

---

## Dataset
- All images used in this assignment are stored in the respective directories.
- Users can replace the images with their own datasets for testing.

---
