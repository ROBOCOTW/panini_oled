# PANINI OLED System Monitor
<img width="2048" height="1152" alt="panini system info" src="https://github.com/user-attachments/assets/0cfe2aaa-cff7-4be6-abe5-256c93bf38e0" />


Display system information on the OLED included with the ROBOCO PANINI case for the NVIDIA Jetson Orin Nano and Orin Nano Super Developer Kits.

## What It Displays

- IP address
- CPU temperature
- CPU usage
- RAM usage

The display refreshes approximately once per second.

## Installation and Usage

Run the following commands on your Jetson, not on your Windows PC.

### 1. Install dependencies

```bash
sudo apt install -y i2c-tools python3-pip python3-smbus
pip3 install adafruit-circuitpython-ssd1306 psutil netifaces Pillow
sudo -H pip3 install --upgrade --force-reinstall jetson-gpio
```

### 2. Check the OLED connection

```bash
sudo i2cdetect -y -r 7
```

The OLED should appear at address `3c`. If it does not, power off the Jetson and check the OLED wiring before continuing.

### 3. Download the example script

```bash
wget https://raw.githubusercontent.com/ROBOCOTW/panini_oled/main/oled_sysinfo.py
```

### 4. Start the display

```bash
python3 oled_sysinfo.py
```

Press `Ctrl+C` to stop the program and clear the display.

These instructions are adapted from the original tutorial linked below. Package installation and hardware access may vary with your JetPack and Python environment. If a command fails, please include the full error message when reporting an issue.## Tutorial

For installation commands, the Python example script, and reference images, see our step-by-step guide:

[Read the PANINI OLED tutorial](https://roboco.tw/blog/panini-oled)

## Hardware

- NVIDIA Jetson Orin Nano or Orin Nano Super Developer Kit
- ROBOCO PANINI case with its included 128 × 64 OLED display

## Feedback

If you run into an issue, please open a GitHub Issue and include:

- Your developer kit and carrier board
- Your JetPack version
- The command you ran and any error messages

## Credits

The original tutorial and example script are credited to the CaveDu Team.

- [Original CaveDu article](https://blog.cavedu.com/2025/12/22/orinnano_panini/)
- [ROBOCO tutorial](https://roboco.tw/blog/panini-oled)

## About PANINI

PANINI is a case designed by ROBOCO in Taiwan. It allows installation without removing the developer kit's original plastic base and includes front power/reset buttons and an OLED display.

[Visit the ROBOCO website](https://roboco.tw/)
