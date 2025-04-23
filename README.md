# Chessboard Analysis

This project implements a robust computer vision solution to analyze chessboard images and accurately count the number of black and white squares, supporting various board orientations and lighting conditions.

## Features

- **Multi-Method Detection**: Implements four complementary approaches for maximum reliability:
  - Pattern-based detection
  - Contour-based detection with multiple binary thresholds
  - OpenCV's chessboard corner detection
  - Grid-based detection as fallback
- **Advanced Preprocessing**: Specialized noise removal and binary image enhancement for chess detection
- **Robust Chessboard Detection**: Handles different orientations, angles, lighting conditions, and partial boards
- **Perspective Correction**: Corrects skewed or angled views of chessboards
- **Square Classification**: Accurately identifies and counts black and white squares
- **Automatic Board Size Detection**: Attempts to detect non-standard board sizes
- **Visual Results**: Provides comprehensive visual feedback of detection and classification processes

## Requirements

- Python 3.6+
- OpenCV
- NumPy
- Matplotlib

## How to Use

### Option 1: Use the Colab Notebook (Recommended)

1. Open the notebook in Google Colab: [Open in Colab](https://colab.research.google.com/github/your-username/chessboard-analysis/blob/main/chessboard_analysis.ipynb)
2. Run all cells in sequence (Runtime > Run all or Ctrl+F9)
3. When prompted, upload your chessboard images
4. View the results, which include:
   - Visualizations of multiple detection methods
   - Counts of white and black squares
   - Comparison of different detection approaches

### Option 2: Local Installation

```bash
git clone https://github.com/your-username/chessboard-analysis.git
cd chessboard-analysis
pip install -r requirements.txt
python improved_chessboard_analysis.py --image path/to/your/chessboard.jpg
```

## Detection Methods

### Method 1: Pattern Detection
Identifies checkerboard patterns directly within the image, useful for clear and well-defined boards.

### Method 2: Contour Detection
Uses multiple binary image variations to detect chessboard squares via contours, with specialized cleaning techniques for optimal results.

### Method 3: Corner Detection
Utilizes OpenCV's `findChessboardCorners()` with enhanced contrast preprocessing for better corner detection.

### Method 4: Grid-based Detection
Acts as a fallback method, using line detection to determine grid size and create a properly divided chessboard grid.

## Advanced Features

- **Automatic Noise Reduction**: Special image cleaning techniques designed specifically for chess patterns
- **Multiple Binary Thresholding**: Testing different binary images to find the optimal segmentation
- **Square Size Validation**: Checks for consistent square sizes to ensure accurate detection
- **Ratio Verification**: Ensures a reasonable ratio between white and black squares
- **Board Size Estimation**: Uses grid line detection to estimate the actual board size

## Troubleshooting

If the system fails to detect a chessboard:
- Ensure the chessboard is clearly visible in the image
- Try adjusting the lighting or angle of the image
- Crop the image to remove background distractions
- The system will attempt multiple detection methods automatically, but extremely poor lighting or complex backgrounds may still cause difficulties

## License

This project is licensed under the MIT License - see the LICENSE file for details. 