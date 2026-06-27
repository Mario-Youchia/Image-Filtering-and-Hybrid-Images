# Image Filtering and Hybrid Images

A computer-vision project that implements two-dimensional spatial correlation directly with NumPy and combines Gaussian low-frequency and high-frequency components to create hybrid images.

A hybrid image changes its dominant interpretation with viewing distance: high-frequency detail is more visible at close range, while low-frequency structure becomes dominant from farther away.

[View and run the notebook on Kaggle](https://www.kaggle.com/code/marioyouchia/image-filtering-and-hybrid-images)

![Dog and cat hybrid-image pipeline](results/dog-cat-pipeline.png)

## Project Overview

The notebook implements the complete workflow for:

- Loading and normalizing aligned source images.
- Creating normalized two-dimensional Gaussian kernels.
- Applying spatial correlation directly with NumPy.
- Supporting grayscale and RGB images.
- Extracting low-frequency image components.
- Extracting high-frequency residuals.
- Combining complementary frequency components into hybrid images.
- Visualizing hybrid images at multiple scales.

The implementation does not rely on a ready-made convolution or correlation function for the main filtering operation.

## Hybrid-Image Method

For each aligned image pair:

1. A Gaussian filter is applied to the first image to preserve its low-frequency structure.
2. A blurred version of the second image is subtracted from the original to isolate high-frequency detail.
3. The low-frequency and high-frequency components are combined.
4. The result is clipped to the valid image-intensity range.
5. The hybrid image is displayed at multiple scales to demonstrate how perception changes with viewing distance.

## Results

### Dog and Cat

![Dog and cat hybrid image at multiple scales](results/dog-cat-hybrid-scales.jpg)

### Einstein and Marilyn

![Einstein and Marilyn hybrid-image pipeline](results/einstein-marilyn-pipeline.png)

### Bird and Plane

![Bird and plane hybrid-image pipeline](results/bird-plane-pipeline.png)

Additional low-frequency, high-frequency, hybrid, and scale-visualization outputs are available in the `results/` directory.

## Repository Structure

```text
.
├── data/                  # Source images used by the project
├── notebook/
│   └── image-filtering-and-hybrid-images.ipynb
├── results/               # Saved hybrid-image outputs and visualizations
├── .gitignore
├── requirements.txt
└── README.md
```

The notebook is the canonical implementation of the project. There are no separate source modules or result-generation scripts.

## Run the Notebook

The recommended way to run the project is through the published Kaggle notebook:

[https://www.kaggle.com/code/marioyouchia/image-filtering-and-hybrid-images](https://www.kaggle.com/code/marioyouchia/image-filtering-and-hybrid-images)

The Kaggle notebook uses the shared **Computer Vision Assets** dataset and locates the following folder:

```text
image-filtering-and-hybrid-images/
```

Generated files are saved under:

```text
/kaggle/working/outputs
```

The notebook copy in this repository is included for source review and project documentation.

## Dependencies

The notebook uses:

- Python
- NumPy
- OpenCV
- Pillow
- Matplotlib
- Jupyter Notebook

## Course Context

Developed for the Computer Vision course at the University of Science and Technology, Zewail City, during Spring 2023.
