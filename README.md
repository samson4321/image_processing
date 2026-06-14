#  Image Processing Histograms

This repository contains a Jupyter Notebook for **Exercise 3** of the SS25 image-processing practical work. The notebook focuses on reading images, converting RGB images to grayscale, creating histograms, comparing histogram methods, and studying the effect of different bin sizes.

## Project Overview

The exercise uses Python image-processing libraries to explore how pixel values are represented and analyzed in both grayscale and color images.

The main tasks are:

1. Read an RGB image and convert it to grayscale.
2. Create histograms of grayscale images.
3. Create histograms of color images.
4. Change histogram bin sizes and compare the results.

## Files

```text
Exercise_3_SS25 (3).ipynb   # Main Jupyter Notebook
me.jpeg                     # Input image used in the notebook; add this image to the repo
README.md                   # Project documentation
```

> Note: The notebook expects an image named `me.jpeg` in the same folder as the notebook. If your image has another name, update the filename in the notebook.

## Requirements

Install the required Python packages before running the notebook:

```bash
pip install numpy matplotlib scikit-image opencv-python jupyter
```

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

2. Install dependencies:

```bash
pip install numpy matplotlib scikit-image opencv-python jupyter
```

3. Start Jupyter Notebook:

```bash
jupyter notebook
```

4. Open:

```text
Exercise_3_SS25 (3).ipynb
```

5. Run the notebook cells from top to bottom.

## Task 1: RGB to Grayscale Conversion

The notebook compares three methods for converting an RGB image to a grayscale image:

### Manual Method

```python
gray_manual = 0.2989 * R + 0.5870 * G + 0.1140 * B
```

This method calculates grayscale intensity using weighted RGB channels. The green channel has the largest weight because human vision is more sensitive to green light.

### scikit-image Method

```python
gray_skimage = io.imread("me.jpeg", as_gray=True)
```

This method loads the image directly as a grayscale image.

### OpenCV Method

```python
gray_cv = cv2.cvtColor(img_cv, cv2.COLOR_BGR2GRAY)
```

OpenCV loads images in BGR format, so conversion is done using OpenCV's built-in color conversion function.

## Task 2: Grayscale Histograms

The notebook creates grayscale histograms using:

- NumPy: `np.histogram()`
- OpenCV: `cv2.calcHist()`
- Matplotlib: `plt.hist()`

A grayscale histogram shows how frequently each intensity value appears in the image. It helps analyze brightness, contrast, exposure, and image quality.

## Task 3: Color Histograms

For color images, histograms are calculated separately for the red, green, and blue channels.

A color histogram provides more information than a grayscale histogram because it shows the distribution of each color channel individually.

## Task 4: Histogram Bin Size Comparison

The notebook compares different bin sizes such as:

- 16 bins
- 64 bins
- 256 bins

Smaller bin sizes create a smoother and simpler histogram but lose detail. Larger bin sizes show more detailed intensity distribution but may appear noisier.

## Discussion Questions

### RQ1: Difference between RGB and grayscale arrays

An RGB image is represented as a 3D array with height, width, and three color channels. A grayscale image is represented as a 2D array with only one intensity value per pixel.

### RQ2: Modifiable histogram parameters

Important histogram parameters include:

- Number of bins
- Intensity range
- Selected color channel
- Image data type and normalization

Changing these parameters affects the shape, detail level, and interpretation of the histogram.

### RQ3: Color histogram vs grayscale histogram

A grayscale histogram represents only intensity distribution. A color histogram represents the distribution of red, green, and blue channels separately, making it useful for color analysis and object detection.

### RQ4: Choosing bin size

The best bin size depends on the task:

- Use fewer bins for simple visualization and noise reduction.
- Use more bins for detailed intensity analysis.
- Use 256 bins for full 8-bit image analysis.

## Applications

Histograms are useful in:

- Image quality assessment
- Contrast analysis
- Thresholding
- Segmentation
- Object detection
- Medical image processing
- Biomedical engineering image analysis

## Author

Klenam Agbadi

## License

This project is for educational purposes.
