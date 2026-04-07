# 3D scene reconstruction

Based on at least 8 correspondences in pixel coordinates (in our case it's 14), it is possible to determine the mutual position of the cameras and perform a 3D reconstruction of all points. We are using two pictures, where one represents left camera M1, and other represents right camera M2 with same calibration

Steps:
- find hidden vertices from objects in both pictures using algorithm for finding hidden points coordinates based on homogenous vector product
- determine the fundamental matrix F from 14 correspondences M1 <-> M2 using DLT algorithm based on SVD decomposition
- determine the basic matrix E from the fundamental matrix F
- decompose the basic matrix E on matrix which represents vector product with vector C and ortogonal matrix A which is matrix of movement using SVD decomposition
- we set right camera position (origin) as coordinate origin, and C vector as left camera position (origin) and A as transition matrix from camera coordinates to the scene coordinates, so we can get camera matricies for both left camera T1 and right camera T2
- using T1 and T2, we do triangulation, and from two corresponding points in pixel coordinates get point in 3D scene coordinate
- used plotly.graph_objects and plotly.express (plotly library) for ploting interactive 3D scene from our coordinates