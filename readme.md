![image](https://github.com/user-attachments/assets/ea7e683e-1d5c-4b0e-be86-2b6c3b4e63db)

# Auto GPU Fan Control

This Python script automatically manages GPU fan speeds and power limits on Ubuntu systems. It monitors GPU temperatures and can reboot the machine if a critical error occurs.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Optional Customization](#optional-customization)
- [License](#license)
- [Screenshots](#screenshots)

## ✨ Features
- **Automatic Fan Control:** Dynamically adjusts GPU fan speed.
- **GPU Monitoring:** Shows temperature, power draw and memory usage via `nvidia-smi`.
- **Safe Reboot:** Reboots the machine if a critical GPU error is detected.
- **Rich Console Output:** Uses the [rich](https://github.com/Textualize/rich) library.

## 📋 Prerequisites
- Ubuntu with NVIDIA drivers installed.
- Python 3 and pip.
- `nvidia-smi` and [`lm-sensors`](https://en.wikipedia.org/wiki/Lm_sensors).
- Required Python modules (e.g. `rich`).

## 🛠 Installation
1. Update package lists:
```bash
sudo apt update && sudo apt upgrade -y
```
2. Install Python and pip:
```bash
sudo apt install python3 python3-pip -y
```
3. Install Python dependencies:
```bash
pip3 install rich
```
4. Install NVIDIA tools and CUDA (optional):
```bash
sudo ubuntu-drivers autoinstall
sudo apt install nvidia-cuda-toolkit -y
```
5. Install and configure `lm-sensors`:
```bash
sudo apt install lm-sensors -y
sudo sensors-detect
```

## 🚀 Usage
Make the script executable and run it:
```bash
chmod +x controlev4.py
python3 controlev4.py
```
The script monitors your GPU and CPU temperatures, automatically adjusting fan speed and power limits. Press `Ctrl+C` to exit.

### 🔧 Optional Customization
Edit the `pl_values` dictionary inside `controlev4.py` to set custom power limits for each GPU.

## 📜 License
This project is licensed under the MIT License.

## 📷 Screenshots
- Change your password here
![image](https://github.com/user-attachments/assets/df0e7b39-6889-4ee3-830c-a204afe86cc8)
- Change PL
![image](https://github.com/user-attachments/assets/4e8ccb75-789d-41b6-a2fd-8772f128f241)
