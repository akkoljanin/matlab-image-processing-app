# MATLAB Image Processing App

A small interactive desktop app built with MATLAB App Designer for experimenting with classic image enhancement techniques. Load an image, pick an operation, and compare the original and the processed result side by side.

## Features

| Operation | What it does | MATLAB functions |
|---|---|---|
| **Contrast Stretching** | Stretches the intensity range between the 5th and 95th percentile to the full range | `stretchlim`, `imadjust` |
| **Median Filter** | Removes salt-and-pepper noise using a 3×3 neighbourhood | `medfilt2` |
| **Laplacian Sharpening** | Sharpens edges by subtracting the Laplacian from the image | `fspecial`, `imfilter` |
| **Gamma Transform** | Power-law brightness correction; gamma is set in the numeric field | `imadjust` |
| **Intensity Thresholding** | Binarizes the image using a threshold (0–255) set with the slider | `imbinarize` |

Other controls: **Browse Image** (JPG, PNG, BMP, TIF), **Save** (export the processed image as PNG or JPG) and **Close**.

All operations are applied to the grayscale version of the loaded image.

## Requirements

- MATLAB R2018a or newer (the app uses `im2gray`, so R2020b+ is recommended)
- Image Processing Toolbox

## Getting started

1. Clone the repository or download `ImageProcessing.mlapp`.
2. Open MATLAB and either double-click the file to open it in App Designer, or run it from the command window:

   ```matlab
   ImageProcessing
   ```

3. Click **Browse Image** and select an image.
4. Click any operation button. The result appears in the right-hand panel.
5. Click **Save** to export the processed image.

## Usage notes

- **Gamma Transform:** enter a value in the small field next to the button. Values below 1 brighten the image, values above 1 darken it. Use a value greater than 0.
- **Intensity Thresholding:** move the slider first, then press the button. Pixels above the threshold become white, the rest black.
- Each operation is applied to the original image, not to the previous result, so operations do not stack.

## Project structure

```
.
├── ImageProcessing.mlapp   # The app (UI layout and callbacks)
└── README.md
```

## Possible improvements

- Chain several operations on top of each other
- Live preview while moving the slider
- Histogram view for the original and processed image
- Support for colour processing instead of grayscale only


