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
Re-orient the point cloud

1. **Plane Detection:**
- Use the RANSAC algorithm to fit a plane model to the points belonging to the ground.
- Extract the plane coefficients (A, B, C, D) from the equation Ax + By + Cz + D = 0.

2. **Reorient the Point Cloud:**
- Calculate the normal vector to the detected plane.
- Determine the rotation needed to align the plane with the YZ plane.
- Apply translation and rotation to the point cloud to center the floor at the origin and align the ground plane with the YZ plane.
