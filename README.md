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

NOTE: This UM7 driver doesn't seem to be working with newer kernel versions on Ubuntu 14.04. For higher update rate (usually larger than 60Hz) it gives a buffer overflow error. I have tested 14.04 kernels upto 4.4.0.111, the highest working version is 4.4.0.62. It also doesn't work on Ubuntu 16.04 kernel version 4.13.x.x, the only version I have tested. The temporary solution is to have 4.4.0.62 installed on your machine(use synaptic manager) and set grub default to boot into this specific version. In /etc/default/grub set GRUB_DEFAULT="1>(ENTRY Number of 4.4.0.62 in the installed kernel list. List starts at 0)".
