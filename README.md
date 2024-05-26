# 3D_Avataar
Playing with a scene point cloud

## Environment setup
```bash
# clone the repo
git clone https://github.com/rohitdhote111/3D_Avataar.git
```

environment.yml file is provided in the repo. Use it to create a conda environment using the below command

```bash
conda env create -f environment.yml
conda activate 3d
```

## Task 1
Re-orient the point cloud (1_Reorient_PC.ipynb)

1. **Plane Detection:**
- Use the RANSAC algorithm to fit a plane model to the points belonging to the ground.
- Extract the plane coefficients (A, B, C, D) from the equation Ax + By + Cz + D = 0.

2. **Reorient the Point Cloud:**
- Calculate the normal vector to the detected plane.
- Determine the rotation needed to align the plane with the YZ plane.
- Apply translation and rotation to the point cloud to center the floor at the origin and align the ground plane with the YZ plane.


## Task 2
Point cloud to Mesh (2_smooth_surface.ipynb)
1. **Normal estimation:**
- Normals are essential for mesh reconstruction tasks because they provide information about surface orientation, which is crucial for generating smooth surfaces.
- orient the estimated normals consistently by aligning them with the tangent plane at each point.

2. **Mesh formation using Poisson's reconstruction algorithm:**
- depth of the octree used in the Poisson reconstruction algorithm by taking multiple trials in CloudCompare software.


## Task 3
unit test case to check and verify the solution from step 1. (3_unit_test_with_transformation)
1. **Transformation to point cloud**
- Applied random rotation and translation transformation to input point cloud

2. **Check**
- The floor plane should be on the YZ plane, hence a should be close to 1, and b, c should be close to 0. where a, b and c are plane parameters.
