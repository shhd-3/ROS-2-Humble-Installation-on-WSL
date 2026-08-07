# ROS-2-Humble-Installation-on-WSL
A setup guide for installing ROS 2 Humble on Ubuntu 22.04 through Windows Subsystem for Linux (WSL) and verifying the installation.
ROS 2 Humble Installation on WSL

# Installation
## 1. Install WSL
Open PowerShell and run as administrator:
```BASH
wsl --install
```
<img width="980" height="397" alt="Screenshot 2026-08-07 195324" src="https://github.com/user-attachments/assets/ca4aff4c-079c-4471-8c45-f2fd1f5a108f" />

Restart the computer after the installation is completed.


## 2. Install Ubuntu 22.04
Open PowerShell again and run:
```bash
wsl --install -d Ubuntu-22.04
```
<img width="972" height="382" alt="Screenshot 2026-08-07 200203" src="https://github.com/user-attachments/assets/a5d85b2a-e482-4ece-be2b-5fbcc1ba230f" />

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
<img width="990" height="405" alt="Screenshot 2026-08-07 204259" src="https://github.com/user-attachments/assets/55bc35e6-efa6-4307-9906-c1b52385510b" />


## 4. Update Ubuntu

Update the package lists:
```bash
sudo apt update
```
<img width="1470" height="281" alt="Screenshot 2026-08-07 221040" src="https://github.com/user-attachments/assets/9d7eef19-325d-4a34-afd1-a23c367e1a0e" />


## 5. Install Required Packages

Install the required packages:
```bash
sudo apt install software-properties-common curl -y
```
<img width="1002" height="51" alt="Screenshot 2026-08-07 204930" src="https://github.com/user-attachments/assets/ae6f3b7e-78ba-4968-83b1-2e8f71305b0b" />


Enable the universe repository:
```bash
sudo add-apt-repository universe
```
<img width="1002" height="22" alt="Screenshot 2026-08-07 205311" src="https://github.com/user-attachments/assets/09d6c6a6-12b2-4692-93c9-f8c56a09919d" />


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
<img width="1476" height="755" alt="Screenshot 2026-08-07 214332" src="https://github.com/user-attachments/assets/43e47ba4-f6ce-40f4-8600-1ed9c70f4421" />

This confirms that ROS 2 Humble has been successfully installed and configured on Ubuntu 22.04 through WSL.
