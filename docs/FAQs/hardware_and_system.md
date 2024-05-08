---
sidebar_position: 1
---
# 6.1 Hardware and System

For certified accessories and purchasing links, please refer to the [Certified Accessories List](https://developer.horizon.cc/documents_rdk/hardware_development/rdk_x3/accessory).

For more details, please refer to the [Frequently Asked Questions](https://developer.horizon.cc/documents_rdk/category/common_questions) section in the Horizon Robotics RDK User Manual.

## What is Horizon Robotics Developer Kit (RDK)?

Horizon Robotics Developer Kit [RDK](https://developer.horizon.cc/documents_rdk/), is a developer kit for robotics based on Horizon's intelligent chips, including **RDK X3**, **RDK X3 Module**, and **RDK Ultra**.

## How to check the system version number?

After the system installation, log in to the system and use the command `apt list --installed | grep hobot` to check the version of the system's core function packages. Use the command `cat /etc/version` to check the major version number of the system.

The system information for version 2.x (using version 2.0.0 as an example) is as follows:

```shell
root@ubuntu:~# apt list --installed | grep hobot

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

hobot-boot/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-bpu-drivers/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-camera/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-configs/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-display/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-dnn/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-dtb/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-io-samples/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-io/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-kernel-headers/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-models-basic/unknown,now 1.0.1 arm64 [installed]
hobot-multimedia-dev/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-multimedia-samples/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-multimedia/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-sp-samples/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-spdev/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-utils/unknown,now 2.0.0-20230530181103 arm64 [installed]
hobot-wifi/unknown,now 2.0.0-20230530181103 arm64 [installed]
root@ubuntu:~#
root@ubuntu:~# cat /etc/version
2.0.0
root@ubuntu:~#

```

The system information for version x (using version 1.1.6 as an example) is as follows:

```shell
root@ubuntu:~# apt list --installed | grep hobot

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

hobot-arm64-bins/unknown,now 1.1.5 arm64 [installed]
hobot-arm64-boot/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-configs/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-desktop/unknown,now 1.1.5 arm64 [installed]
hobot-arm64-dnn-python/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-gpiopy/unknown,now 1.1.5 arm64 [installed]
hobot-arm64-hdmi-sdb/unknown,now 1.1.5 arm64 [installed]
hobot-arm64-includes/unknown,now 1.1.5 arm64 [installed]
hobot-arm64-libs/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-modules/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-sdb-ap6212/unknown,now 1.1.6 arm64 [installed]
hobot-arm64-srcampy/unknown,now 1.1.5 arm64 [installed]
hobot-linux-headers/unknown,now 1.1.5 arm64 [installed]
hobot-models-basic/unknown,now 1.0.1 arm64 [installed]
hobot-sp-cdev/unknown,now 1.1.6 arm64 [installed]
root@ubuntu:~#
root@ubuntu:~# cat /etc/version
x3_ubuntu_v1.1.6
root@ubuntu:~#
```

System version and RDK platform hardware compatibility:

System version explanation:

- Version 2.x system: Based on the RDK Linux open-source code package, it supports the full range of RDK X3, RDK X3 Module, and other hardware.

- Version 1.x system: Based on a closed-source Linux system, it is a historical version and only supports RDK X3 hardware.

**Note:**

- **The 1.x version system cannot be directly upgraded to the 2.x version system using the apt command. It needs to be reinstalled the system by burning the image. Please refer to the [system installation guide](https://developer.horizon.cc/documents_rdk/installation/install_os).**

- **The 2.x version of tros.b only supports the 2.x version system, and the 1.x version of tros.b only supports the 1.x version system.**

## Considerations for plugging and unplugging the camera:

**It is strictly prohibited to plug or unplug the camera while the development board is powered on, as it can easily damage the camera module.**

## How to connect the serial cable?

One end of the serial cable (white) is connected to the RDK X3. Since the interface has a groove, the correct orientation is usually maintained. The other end is connected to the serial port adapter board. Pay close attention to the connection diagram below:

![](./image/hardware_and_system/connect.jpg)

## What are the power requirements for RDK X3?

RDK X3 is powered through a USB Type C interface and is compatible with QC and PD fast charging protocols. It is recommended to use a power adapter that supports QC and PD fast charging protocols, or at least a power adapter with **5V DC 2A** output to supply power to the development board.

**Note: Please do not use the USB interface of a PC to power the development board, as it may cause abnormal operation of the board due to insufficient power supply (such as no HDMI output (completely black screen) after RDK X3 is powered on, the green light is not off, after connecting the serial port, the system keeps rebooting repeatedly and cannot enter the operating system)**.

## Does RDK X3 have a recommended SD card?

It is recommended to use a high-speed C10 SD card with a capacity of at least 16GB. Older cards may have issues with booting the image.

Kingston: <https://item.jd.com/25263496192.html>

SanDisk: <https://item.jd.com/1875992.html#crumb-wrap>

## How to connect F37 and GC4663 MIPI cameras?

The F37 and GC4663 camera modules are connected to the development board via a 24-pin FPC cable with opposite side connectors. **Note that the blue side of the cable should be facing up when inserting it into the connector**. The connection diagram for the F37 camera is shown below:

![](./image/hardware_and_system/image-X3-PI-Camera.jpg)

After a successful connection, power on the board and execute the following command:

```bash
cd /app/ai_inference/03_mipi_camera_sample
sudo python3 mipi_camera.py
```

The HDMI output of the algorithm rendering result is shown in the following image, which detects a "teddy bear", a "cup", and a "vase" in the sample image.

![](./image/hardware_and_system/image-20220511181747071.png)

```text
Enter the command: i2cdetect -y -r 1   
F37：
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- UU -- -- -- -- 
40: 40 -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- --   

GC4663：
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- -- -- -- -- -- 29 -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- UU -- -- -- -- 
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- --                         
```

## How to view the CPU, BPU, and other running statuses of RDK X3?

```bash
sudo hrut_somstatus
```

## How to set up auto-startup?

You can achieve auto-startup functionality by adding commands to the end of the file "/etc/rc.local" using the following command:

```bash
sudo vim /etc/rc.local
```

Then add the following lines at the end of the file:

```bash
#!/bin/bash -e
# 
# rc.local
#re
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

#!/bin/sh

chmod a=rx,u+ws /usr/bin/sudo
chown sunrise:sunrise /home/sunrise

which "hrut_count" >/dev/null 2>&1
if [ $? -eq 0 ]; then
        hrut_count 0
fi

# Insert what you need
```