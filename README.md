# Simple_errors

### ImportError: /opt/ros/kinetic/lib/python2.7/dist-packages/cv2.so: undefined symbol: PyCObject_Type

1. This problem is caused by ROS adding `/opt/ros/kinetic/lib/python2.7/dist-packages` to the python path.
2. Added `export PYTHONPATH="/home/anirban/anaconda3/lib/python3.6/site-packages:$PYTHONPATH"` to bashrc.
3. Added `import sys` and `sys.path.remove('/opt/ros/kinetic/lib/python2.7/dist-packages')` to the beginning of python script.


### cv2.error: OpenCV(3.4.1) /opt/conda/conda-bld/opencv-suite_1527005194613/work/modules/highgui/src/window.cpp:636: error: (-2) The function is not implemented. Rebuild the library with Windows, GTK+ 2.x or Carbon support. If you are on Ubuntu or Debian, install libgtk2.0-dev and pkg-config, then re-run cmake or configure script in function cvShowImage

1. Use :
*`conda remove opencv`
*`conda install -c menpo opencv`
*`pip install --upgrade pip`
*`pip install opencv-contrib-python`
