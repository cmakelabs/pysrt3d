# pysrt3d

python binding for [*SRT3D: Region-Based 6DoF Object Tracking*](https://github.com/DLR-RM/3DObjectTracking/tree/master/SRT3D)


### Modification
#### Automatical body-diameter calculation
You don't need to specify `max_body_diameter` manually, just as [*M3T*](https://github.com/DLR-RM/3DObjectTracking/tree/master/M3T).

#### Kullback-Leibler divergence based confidence assessment 
If the predicted pose is good (close to the reality), the mean value of each correspondence line will be zero (at the center, without offset). We calculate KL divergence for each correspodence line and the optimal one: $\mathcal{N}(0, \sigma_{min}^2)$.

#### Thresholds for initialization and tracking
We define thresholds for initialization and tracking (you can manually set them), so that you can easily align the object to the virtual one before start tracking.

#### Independent multi-model tracing
The confidences are calculated independently. You can easily add models and get their information (pose, conf., etc.).


### Installation
Make sure that you have installed the following packages:
- OpenGL
- GLEW
- glfw3
- Eigen3
- OpenCV 3/4
- OpenMP

Your compilation environment should support `C++ 17`.

```
cd ${repo_root}
pip install .
```


### Demo
```
cd ${repo_root}/example
python demo.py
```


### Interface
Just follow `example/demo.py` or `source/pysrt3d/pysrt3d.cpp`.