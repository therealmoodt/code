Auto GPU Fan Control
This project provides a Python script to automatically adjust GPU fan speeds on Ubuntu based on the temperature. The script also handles power limits (PL) for each GPU and can reboot the machine in case of critical errors.

Table of Contents
Features
Prerequisites
Installation Guide
Usage
Optional Configuration
License
Features
Automatic Fan Control: Adjusts GPU fan speed dynamically based on temperature.
GPU Monitoring: Displays temperature, fan speed, power draw, and memory usage for each GPU using nvidia-smi.
Safe Reboot: Automatically reboots the machine if a critical GPU error is detected.
Detailed Console Output: Uses the rich library for enhanced command-line interface aesthetics.
Prerequisites
Before running the script, ensure that your Ubuntu machine is set up with the following:

A fresh Ubuntu installation.
Python 3 and pip.
NVIDIA drivers and CUDA toolkit (if applicable).
nvidia-smi (comes with NVIDIA drivers).
lm-sensors for reading hardware sensor data.
The required Python modules.
Installation Guide
Follow these steps on a fresh Ubuntu installation:

Step 1: Update & Upgrade the System
💾 Update package lists and upgrade existing packages:

sudo apt update && sudo apt upgrade -y
- Step 2: Install Python 3 and pip
🐍 Ensure that Python 3 and pip are installed:


sudo apt install python3 python3-pip -y
- Step 3: Install Required Python Modules
📦 Install the rich library for enhanced terminal output:


pip3 install rich
- Step 4: Install NVIDIA Drivers and CUDA (if applicable)
🎮 Install the NVIDIA drivers and CUDA toolkit if you use NVIDIA GPUs:


sudo ubuntu-drivers autoinstall
sudo apt install nvidia-cuda-toolkit -y
Remember to reboot your machine after installing the drivers.

- Step 5: Verify NVIDIA Tools
🖥️ Ensure nvidia-smi is installed (it comes with the NVIDIA drivers):


nvidia-smi
If you need the py-nvtool.py (utilized in the script), make sure it is located in the path specified in the script (/home/<your_username>/py-nvtool.py). Alternatively, adjust the path within the script.

- Step 6: Install lm-sensors
🌡️ Install and configure lm-sensors for temperature monitoring:


sudo apt install lm-sensors -y
sudo sensors-detect
Answer 'yes' to the proposed questions to detect your sensors.

- Step 7: Configure Sudoers (Optional)
🔐 Optionally, configure sudoers to run the NVIDIA tool script without a password prompt:


sudo visudo
Add the following line (replace your_username with your actual username):

plaintext

your_username ALL=(ALL) NOPASSWD: /usr/bin/python3 /home/<your_username>/py-nvtool.py
Warning: Using this configuration may present security risks. Make sure you understand the implications.

- Step 8: Save Your Script & Run It
📁 Place your updated controlev4.py in a directory of your choice and make it executable:

chmod +x controlev4.py
Then run the script:

python3 controlev4.py

Usage
The script will continuously monitor your GPU and CPU temperatures.

Based on the GPU temperature, it automatically adjusts the fan speed and power limits.

In case of a critical error (e.g., GPU temperature not available), the script will initiate a system reboot.

Use Ctrl+C to stop the script gracefully.

Optional Configuration
Customize Power Limits: Modify the pl_values dictionary in the script to set individual power limits (PL) for each GPU.

Script Path: Ensure that the path for py-nvtool.py in the script corresponds to its actual location on your system.

Auto Reboot: The script is configured to automatically reboot the machine upon detecting a critical GPU error. Edit the initiate_reboot function if needed.

License
This project is licensed under the MIT License. See the LICENSE file for details.
