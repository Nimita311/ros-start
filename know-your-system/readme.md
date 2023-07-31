# Know Your System

You have a robot. Congratulations! Now you possess the power to do amazing things with it. But with this great power comes the inalienable responsibility of maintaining your robotic system. If you are familiar with [pets vs. cattle analogy](https://cloudscaling.com/blog/cloud-computing/the-history-of-pets-vs-cattle) in DevOps, you would realize your robot is your pet who needs your care. Wearing a system admin's hat is what a roboticist has to do from time to time.

To begin developing robotics software, get familiarized with your system.

## Compute Platform

An off-the-shelf ROS enabled robot usually comes with a computer that runs Ubuntu. Use the following commands to discover basic information about that computer.

You are encouraged to learn more about these commands and how to interpret their output in your own time.

**Operating System**
```
$ cat /etc/os-release
```
(In technical documents, `$` at the beginning of an instruction usually means what follows it is intended to run on the command line.)

Example output:
```
NAME="Ubuntu"
VERSION="20.04.6 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.6 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal
```

**Total Memory**
```
$ grep MemTotal /proc/meminfo
```
```
MemTotal:        8142256 kB
```

**Disk Space and Mounts**
```
$ df -h
```
```
Filesystem      Size  Used Avail Use% Mounted on
overlay         118G   15G   97G  14% /
tmpfs            64M     0   64M   0% /dev
shm              64M     0   64M   0% /dev/shm
grpcfuse        927G  523G  404G  57% /code
/dev/vda1       118G   15G   97G  14% /tmp/.X11-unix
tmpfs           3.9G     0  3.9G   0% /sys/firmware
```

**CPU**
```
$ lscpu
```
```
Architecture:                    aarch64
CPU op-mode(s):                  64-bit
Byte Order:                      Little Endian
CPU(s):                          4
On-line CPU(s) list:             0-3
Thread(s) per core:              1
Core(s) per socket:              4
Socket(s):                       1
Vendor ID:                       0x00
Model:                           0
Stepping:                        0x0
BogoMIPS:                        48.00
Vulnerability Itlb multihit:     Not affected
Vulnerability L1tf:              Not affected
Vulnerability Mds:               Not affected
Vulnerability Meltdown:          Not affected
Vulnerability Mmio stale data:   Not affected
Vulnerability Spec store bypass: Vulnerable
Vulnerability Spectre v1:        Mitigation; __user pointer sanitization
Vulnerability Spectre v2:        Not affected
Vulnerability Srbds:             Not affected
Vulnerability Tsx async abort:   Not affected
Flags:                           fp asimd evtstrm aes pmull sha1 sha2 crc32 atomics fphp asimdhp cpuid asimdrdm jscvt fcma lrcpc dcpop sha3 asimddp sha512 asimdfhm dit uscat ilrcpc flagm ssbs sb paca pacg dcpodp flagm2 frint
```

## ROS Installation

```
$ printenv | grep ROS
```
```
ROS_VERSION=1
ROS_PYTHON_VERSION=3
ROS_PACKAGE_PATH=/opt/ros/noetic/share
ROSLISP_PACKAGE_DIRECTORIES=
ROS_ETC_DIR=/opt/ros/noetic/etc/ros
ROS_MASTER_URI=http://localhost:11311
ROS_ROOT=/opt/ros/noetic/share/ros
ROS_DISTRO=noetic
```
