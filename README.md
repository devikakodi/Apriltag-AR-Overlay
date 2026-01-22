# AprilTag Pose Estimation and Augmented Reality Overlay

## Overview
This project demonstrates camera-based AprilTag detection, 6-DoF pose
estimation, and augmented reality overlay using OpenCV and geometric
computer vision techniques. The system detects AprilTags in a monocular
image, estimates the tag’s spatial pose using camera calibration data,
and projects a 3D cube onto the image to visualize the estimated pose.

<img width="353" height="332" alt="Screenshot 2026-01-22 at 10 41 03 AM" src="https://github.com/user-attachments/assets/fe94753e-a86c-498d-a221-644c0c7945b1" />

The environment is entirely image-based, with all perception derived
from camera input and a precomputed calibration model.


## Methodology
- Camera intrinsic parameters and distortion coefficients are loaded
  from calibration files.
- AprilTags are detected using the `apriltag` library.
- Corner points of detected tags are used to solve the Perspective-n-Point
  (PnP) problem via `cv2.solvePnP`.
- The estimated pose is used to project a 3D cube onto the image plane,
  providing a visual verification of pose accuracy.

AprilTag detection is first performed to identify tag ID and corner locations, which are then used for camera pose estimation and augmented reality overlay

## Key Features
- AprilTag detection using monocular vision
- Camera calibration and distortion correction
- 6-DoF pose estimation via solvePnP
- Augmented reality cube projection
- Visualization of pose consistency from multiple viewpoints

## Sample Results
Below are sample outputs illustrating successful AprilTag detection and
3D cube projection aligned with the estimated pose.

<img width="431" height="565" alt="Screenshot 2026-01-22 at 10 40 54 AM" src="https://github.com/user-attachments/assets/23d20add-ded7-43da-ad5b-707c951fcaa6" />

<img width="427" height="368" alt="Screenshot 2026-01-22 at 10 43 35 AM" src="https://github.com/user-attachments/assets/0a745698-ff94-4381-a900-2cdce1123aec" />

## Running the Code

1. Ensure the `apriltag` folder, calibration files (`calibration_set1.npz`, `calibration_set2.npz`), and `Main-code.ipynb` are located in the same directory.
2. Open `Main-code.ipynb` using Jupyter Notebook or JupyterLab.
3. Update the image path in the notebook to point to the AprilTag image to be processed.
4. Run the notebook cells sequentially to detect the AprilTag and visualize pose estimation results.

