# Task4_SmartMethods.
This project explains how Ubuntu Linux was installed in a virtual machine and how ROS was set up. During installation, a Python version mismatch caused ROS packages to fail. The issue was fixed by selecting the correct Python version and rebuilding the ROS workspace.
# 🐧 Linux Installation & ROS Setup  
This document explains how I installed Ubuntu Linux and set up ROS, including one installation issue I faced and how I solved it.

---

## 📌 1. Installing Linux (Ubuntu)

I downloaded Ubuntu and installed it inside a virtual machine (VirtualBox / VMware).  
I created a new VM, assigned RAM and CPU, booted from the Ubuntu ISO, and completed the installation normally.

---

## 📌 2. Installing ROS

I installed ROS by updating the system, adding the ROS repository, and running the installation commands.  
After installation, I activated ROS using:

```bash
source /opt/ros/noetic/setup.bash


---

⚠️ 3. Issue & Solution (Python Version Mismatch)

# Issue:
I encountered an ImportError while running ROS because the Python version used by my system did not match the version required by ROS. This caused ROS packages (such as rclpy) to fail during import.

# Solution:
I unified the Python version by installing the correct Python release and selecting it as the default:

sudo apt install python3
sudo update-alternatives --config python

Then I rebuilt the ROS workspace:

colcon build --symlink-install

After applying these steps, ROS ran successfully without any errors.
