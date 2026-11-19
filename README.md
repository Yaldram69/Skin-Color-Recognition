# Skin Color Recognition

A webcam demo that detects faces with MTCNN and estimates a skin tone label for each face. For each detected face, the script builds a skin mask in HSV colour space, then classifies the skin tone from hue, saturation and value histograms of the masked region.

## Features

- Face detection with MTCNN (`mtcnn` package)
- HSV skin-colour mask (hue 0-20, saturation 40-255, value 80-255) with morphological clean-up
- Histogram-based skin tone classification, shown as a label above each face box
- Live webcam window; press `q` to quit

## Project structure

- `Skin Color Recognition/` - project folder
  - `Skin Color Recognition.ipynb` - main notebook with the classifier function and the webcam loop (final cell)
  - `demo/` - demo videos (`skin color demo.mp4`, `Feb-10-2025_18-34-17.mp4`)
  - `.ipynb_checkpoints/` - Jupyter autosave files (can be ignored)

## Requirements

Packages imported by the notebook:

- mtcnn (depends on TensorFlow or Keras)
- opencv-python (`cv2`)
- numpy
- matplotlib (used for display cells)

Install:

```bash
pip install mtcnn opencv-python numpy matplotlib
```

`mtcnn` pulls in TensorFlow, so a working TensorFlow install is needed.

## Installation

```bash
pip install mtcnn opencv-python numpy matplotlib
```

## Usage

Open the notebook in Jupyter and run the cells in order:

```bash
jupyter notebook "Skin Color Recognition/Skin Color Recognition.ipynb"
```

- Input: webcam (`cv2.VideoCapture(0)`) in the final cell
- Output: window "Webcam Feed with Face and Skin Tone", with a face box and skin tone label
- Press `q` to stop the webcam loop

## Notes

- The notebook contains an earlier cell that reads `D:\blueimage.jpg` from a local Windows path. That cell is an experiment and is not needed for the webcam demo.
- The skin tone classification is a heuristic based on the histogram analysis. It is not a validated skin tone model, and results depend heavily on lighting and camera white balance.
- The demo videos in `demo/` are included as examples.
- Some notebook cells are duplicates of the same function, from iterative editing.
