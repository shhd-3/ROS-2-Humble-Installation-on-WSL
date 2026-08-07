# ROS-2-Humble-Installation-on-WSL
A setup guide for installing ROS 2 Humble on Ubuntu 22.04 through Windows Subsystem for Linux (WSL) and verifying the installation.
ROS 2 Humble Installation on WSL

# Installation
## 1. Install WSL
Open PowerShell and run:
```BASH
wsl --install
```
Restart the computer after the installation is completed.


## 2. Install Ubuntu 22.04
Open PowerShell again and run:
```bash
wsl --install -d Ubuntu-22.04
```
Create a Linux username and password when prompted.


## 3. Verify the Ubuntu Version
Open Ubuntu and check the installed version:
```bash
lsb_release -a
```
The installed version should be:
```bash

Ubuntu 22.04.5 LTS
Codename: jammy
```

## 4. Update Ubuntu

Update the package lists:
```bash
sudo apt update
```
## 5. Install Required Packages

Install the required packages:
```bash
sudo apt install software-properties-common curl -y
```

Enable the universe repository:
```bash
sudo add-apt-repository universe
```

## 6. Add the ROS 2 Repository
Download the ROS 2 repository key:
```bash

sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
Add the ROS 2 repository:
```bash

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu jammy main" | sudo tee /etc/apt/sources.list.d/ros2.list
```

Update the package lists:
```bash

sudo apt update
```
## 7. Install ROS 2 Humble
Install the ROS 2 Humble Desktop package:
```bash

sudo apt install ros-humble-desktop -y
```
Wait for the installation to complete.
## 8. Configure ROS 2
Source the ROS 2 Humble environment:
```bash

source /opt/ros/humble/setup.bash
```
## 9. Verify the Installation
Check the installed ROS distribution:
```bash

echo $ROS_DISTRO
```
The expected output is:
```bash

humble
```
This confirms that ROS 2 Humble has been successfully installed and configured on Ubuntu 22.04 through WSL.
