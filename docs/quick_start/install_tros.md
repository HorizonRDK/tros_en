---
sidebar_position: 2
---
# 1.2 apt installation and upgrade

This section introduces how to use apt to install TogetheROS.Bot on Horizon RDK.

## Horizon RDK

Prerequisites

- The environment preparation in section 1.1 has been completed.
- The Horizon RDK system has been installed with version 2.x.
- The Horizon RDK can access the internet normally.
- The Horizon RDK can be accessed remotely via SSH.

### Installation

**Note: The IP address of the Horizon RDK used here is 10.64.61.241. Replace it with your IP address during installation.**

Login to the Horizon RDK

```shell
ssh root@10.64.61.241
```

Install the tros.b package, `sudo apt update; sudo apt install tros`

**Note: If you encounter the error `E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).' after running the installation command, please execute the command `apt --fix-broken install` to install the related dependencies before installing tros.b.**

After the installation is complete, check the files in the /opt directory

```bash
root@ubuntu:/userdata# ls /opt/
hobot  tros
```
The tros.b is installed in the /opt directory.

### Upgrade tros.b

Login to Horizon RDK:

```shell
ssh root@10.64.61.241
```

Upgrade tros.b deb package:

```shell
sudo apt update
sudo apt upgrade
```

Check the current version of tros.b:

```bash
root@ubuntu:~# apt show tros
Package: tros
Version: 2.0.0-20230523223852
Maintainer: kairui.wang <kairui.wang@horizon.ai>
Installed-Size: unknown
Depends: hobot-models-basic, tros-ros-base, tros-ai-msgs, tros-audio-control, tros-audio-msg, tros-audio-tracking, tros-body-tracking, tros-dnn-benchmark-example, tros-dnn-node, tros-dnn-node-example, tros-dnn-node-sample, tros-elevation-net, tros-gesture-control, tros-hand-gesture-detection, tros-hand-lmk-detection, tros-hbm-img-msgs, tros-hobot-app-xrrobot-body-tracking, tros-hobot-app-xrrobot-gesture-control, tros-hobot-codec, tros-hobot-cv, tros-hobot-falldown-detection, tros-hobot-hdmi, tros-hobot-image-publisher, tros-hobot-mot, tros-hobot-usb-cam, tros-image-subscribe-example, tros-img-msgs, tros-imu-sensor, tros-line-follower-model, tros-line-follower-perception, tros-mipi-cam, tros-mono2d-body-detection, tros-mono2d-trash-detection, tros-mono3d-indoor-detection, tros-parking-perception, tros-parking-search, tros-rgbd-sensor, tros-websocket, tros-xrrobot, tros-xrrobot-msgs
Download-Size: 980 B
APT-Manual-Installed: yes
APT-Sources: http://sunrise.horizon.cc/ubuntu-rdk focal/main arm64 Packages
Description: TogetheROS Bot

```

It can be seen that the current version of tros.b has been upgraded to version 2.0.0.
