ros-drivers-um7
===============

ROS driver for the CH Robotics UM7 inertial measurement device.
Supports standard data and mag topics as well as providing temperature and rpy outputs.
  See the ROS wiki for details:  http://wiki.ros.org/um7

===============
When interfacing with /dev/tty* devices, remember to have setup the following:

A) Add your user profile to accounts:

sudo adduser $USER dialout
sudo adduser $USER plugdev

B) Change permissions if necessary (replace * with <USBn/ACMn/...> if specific device is to be changed)

sudo chmod a+rw /dev/ttyUSB*
sudo chmod a+rw /dev/ttyACM*
