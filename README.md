# Retinal Blood Vessel Segmentation

This project implements classical computer vision approaches for retinal blood vessel segmentation using the DRIVE dataset.

## Overview

The implementation uses Anisotropic Directional Laplacian of Gaussian (ALoG) filters to detect blood vessels in retinal images. The method is scale and rotation invariant, capable of detecting vessels of different widths and orientations.

## Dataset

The project uses the DRIVE (Digital Retinal Images for Vessel Extraction) dataset, which consists of:
- Training images
- Test images
- Manual annotations (ground truth)
- Field of View (FOV) masks

## Implementation Details

The main algorithm includes:
- Multi-scale vessel detection using different sigma values
- Directional filtering using multiple orientations (18 angles from 0° to 180°)
- Anisotropic filtering with elongation factors
- Artifact thresholding to remove noise
- Field of View masking

### Key Parameters
```python
num_orientations = 18  # Number of directional filters
sigma_values = [2.0]   # Scale parameters
elongation_factors = [3.0]  # Filter elongation factors
```

## Project Structure

```
DRIVE/
├── test/
│   ├── 1st_manual/
│   ├── 2nd_manual/
│   ├── images/
│   └── mask/
└── training/
    ├── 1st_manual/
    ├── images/
    └── mask/
```

## Requirements

- Python 3.x
- NumPy
- OpenCV (cv2)
- Matplotlib
- Jupyter Notebook

## Usage

The implementation is available in the Jupyter notebook `RBVS_Classical.ipynb`. To run the segmentation:

1. Ensure the DRIVE dataset is properly structured in the project directory
2. Open and run the `RBVS_Classical.ipynb` notebook
3. The results will show the vessel response map alongside the manual annotation for comparison

## Results

The algorithm outputs vessel probability maps that can be compared with manual annotations provided in the DRIVE dataset.
