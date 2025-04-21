# Chessboard Analysis

## Overview
This project utilizes computer vision techniques to analyze images of chessboards, accurately detecting and classifying black and white squares. The solution handles various challenges including different orientations, lighting conditions, and potential image distortions.

## Features
- Chessboard detection using multiple methods
- Perspective correction for skewed images
- Square detection and classification
- Validation of results against expected counts
- Support for various chessboard sizes (standard 8x8 and others)

## Implementation Details

### Technical Approach
The solution employs a multi-method pipeline to maximize accuracy:

1. **Image Preprocessing**
   - Grayscale conversion
   - Gaussian blur for noise reduction
   - Adaptive thresholding for handling different lighting conditions
   - Morphological operations to enhance features

2. **Detection Methods**
   - **Method 1: Corner Detection** - Utilizes OpenCV's `findChessboardCorners` function to detect the internal corners of the chessboard
   - **Method 2: Contour Detection** - Falls back to contour detection and perspective transformation when corner detection fails

3. **Square Classification**
   - Pattern-based approach (alternating colors)
   - Brightness analysis for classification validation
   - Verification against expected counts for the detected grid size

### Algorithm Highlights
- Perspective correction to handle skewed boards
- Grid size detection using Hough line transform
- Robust square classification combining pattern-based and pixel-intensity approaches
- Validation mechanism to ensure the counts make sense for the detected board size

## Requirements
- Python 3.6+
- OpenCV (`opencv-python-headless`)
- NumPy
- Matplotlib
- PIL (Pillow)

## Usage Instructions

### Running in Google Colab

1. **Open the Notebook**
   - Access the notebook using the provided Google Colab link

2. **Install Dependencies**
   - The first cell in the notebook installs the required libraries:
   ```python
   !pip install opencv-python-headless
   ```

3. **Upload Images**
   - Use the file upload functionality included in the notebook
   - You will be prompted to select images after running the upload cell

4. **Run the Analysis**
   - Execute the cells sequentially to process the uploaded images
   - Results will be displayed with visualizations including:
     - Original image
     - Binary preprocessed image
     - Detected chessboard
     - Perspective-corrected view
     - Grid detection
     - Square classification with counts

5. **Interpret Results**
   - The notebook displays annotated images with squares marked:
     - Yellow outlines for white squares
     - Red outlines for black squares
   - Square counts are validated against expected values for the detected board size

## Results and Validation
The solution provides detailed output for each processed image:
- Visual representation of each processing step
- Square counts (white and black)
- Validation check comparing actual vs. expected counts
- Success or failure indicators based on validation

## Challenges Addressed
- **Varying Orientations**: Perspective correction handles tilted or angled boards
- **Lighting Variations**: Adaptive thresholding normalizes different lighting conditions
- **Distortions**: Multiple detection methods ensure robustness to image imperfections
- **Different Board Sizes**: Automatic detection of grid dimensions beyond standard 8x8

## Future Improvements
- Piece detection and classification
- Board state analysis (game position recognition)
- Support for unusual board colors beyond standard black and white
- Real-time analysis from video streams

## Video Explanation
A video walkthrough explaining the code and demonstrating the results is available (https://drive.google.com/file/d/1ajeiZ07u54GMuD1psGjA8IrlOLfTF9EV/view?usp=sharing).
