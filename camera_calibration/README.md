# Camera Calibration

This project implements camera calibration using correspondences between 3D points and their projections in a 2D image. The goal is to reconstruct the camera parameters and visualize its position relative to a 3D cube.

- estimation of the camera projection matrix using SVD
- decompotion into:
    - Intrinsic matrix (K) – camera calibration parameters
    - Extrinsic matrix (A) – camera orientation
    - Camera center (C) – camera position in 3D space
- visualization of:
    - 3D cube
    - world coordinate system
    - camera position and orientation