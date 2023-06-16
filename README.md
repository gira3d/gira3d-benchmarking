# GIRA3D Benchmarking
Tools to compare with existing mapping frameworks via python bindings.

Currently supports:
1. Octomap [1]: Wrapper over `ColorOcTree` class.
2. NDTmap [2]: Wrapper over a custom NDT Cell that includes color in each cell.

Get this repository by:
```
git clone git@github.com:gira3d/gira3d-benchmarking.git --recursive
```

## Dependencies
This meta-package assumes you are in a virtual environment set up via the meta-package `gira3d-reconstruction`.
If you have not set this up yet, please head to https://github.com/gira3d/gira3d-reconstruction and set up
the python virtual environment along with the Open3D, Pybind11, and Eigen3 dependencies.

`libpcl-dev` = 1.11 is required for NDTMap. On Ubuntu, install via `sudo apt install libpcl-dev`.

## Build
Just run
```
./build
```
MacOS and Windows are not supported.

## Usage
To update the `PYTHONPATH`, use
```
source workon
```
### NDTMap
There is a helper script provided in `wet/src/ndt_map_py/test/test_ndt.py`. Reads the point cloud
in `copier.npz` (make sure you use Git LFS to pull this point cloud). Visualizes the reconstructed intensity
map from NDTMap using Open3D.

### Octomap
There is a helper script provided in `wet/src/octomap_py/test_scripts/test_color_pcld.py`. Same functionality
as in NDTMap script above.

## References
[1] A. Hornung, K. M. Wurm, M. Bennewitz, C. Stachniss, and W. Burgard, “OctoMap: an efficient probabilistic 3D mapping framework based on octrees,” Autonomous Robots, vol. 34, no. 3, pp. 189–206, Apr. 2013, doi: 10.1007/s10514-012-9321-0.

[2] J. Saarinen, H. Andreasson, T. Stoyanov, J. Ala-Luhtala, and A. J. Lilienthal, “Normal Distributions Transform Occupancy Maps: Application to large-scale online 3D mapping,” in 2013 IEEE International Conference on Robotics and Automation, May 2013, pp. 2233–2238. doi: 10.1109/ICRA.2013.6630878.
