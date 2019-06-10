# Simple_errors

### ImportError: /opt/ros/kinetic/lib/python2.7/dist-packages/cv2.so: undefined symbol: PyCObject_Type
1. This problem is caused by ROS adding '/opt/ros/kinetic/lib/python2.7/dist-packages' to the python path.
2. Added 'export PYTHONPATH="/home/anirban/anaconda3/lib/python3.6/site-packages:$PYTHONPATH"' to bashrc.
3. Added 'import sys' and 'sys.path.remove('/opt/ros/kinetic/lib/python2.7/dist-packages')' to the beginning of python script.

