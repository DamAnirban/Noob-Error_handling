# Simple_errors

### ImportError: /opt/ros/kinetic/lib/python2.7/dist-packages/cv2.so: undefined symbol: PyCObject_Type

1. This problem is caused by ROS adding `/opt/ros/kinetic/lib/python2.7/dist-packages` to the python path.
2. Added `export PYTHONPATH="/home/anirban/anaconda3/lib/python3.6/site-packages:$PYTHONPATH"` to bashrc.
3. Added `import sys` and `sys.path.remove('/opt/ros/kinetic/lib/python2.7/dist-packages')` to the beginning of python script.

> Status : Solved


### cv2.error: OpenCV(3.4.1) /opt/conda/conda-bld/opencv-suite_1527005194613/work/modules/highgui/src/window.cpp:636: error: (-2) The function is not implemented. Rebuild the library with Windows, GTK+ 2.x or Carbon support. If you are on Ubuntu or Debian, install libgtk2.0-dev and pkg-config, then re-run cmake or configure script in function cvShowImage

1. This occurs if you have installed OpenCV using the opencv-python pip package or simple conda install opencv. Instead use conda menpo. Follow :
2. `conda remove opencv`
3. `conda install -c menpo opencv`
4. `pip install --upgrade pip`
5. `pip install opencv-contrib-python`

> Status : Solved

### Timed out waiting for transform from base_link to map to become available before running costmap, tf error: canTransform: target_frame map does not exist.. canTransform returned after 354.222 timeout was 0.1.

1. This occurs when there is no tf between map to odom. 
2. It was solved by 2 methods - first, the order of launching `wheel odometry -> visual -> navigation stack` should be correct. Second, make sure that the parameter `obstacles/laser/topic` to `/scan` in file `costmap_local.yaml` and `costmap_global_static.yaml` . Otherwise the laserscan won't be received the obstacles layer in local costmap.

> Status : Solved
