# Simple_errors

### ImportError: /opt/ros/kinetic/lib/python2.7/dist-packages/cv2.so: undefined symbol: PyCObject_Type
This problem is caused by ROS adding /opt/ros/kinetic/lib/python2.7/dist-packages to the python path.
export PYTHONPATH="/home/anirban/anaconda3/lib/python3.6/site-packages:$PYTHONPATH"
