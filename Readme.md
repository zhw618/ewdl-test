## 说明
forked from [nicola-sysdesign/ewdl-test](https://github.com/nicola-sysdesign/ewdl-test)

Based on SOEM, control the INOVANCE InoSV660N servo drive to operate in **CSP mode** (Cyclic Synchronous Position Mode).

基于SOEM, 控制汇川SV660N伺服驱动器运行于 **CSP模式** 下.

## Requirements :
### Hardware:
- I use a RaspberryPi 3B+
### Operating System:
- RaspiOS Buster (2020-05-27-raspios-buster-lite-armhf.zip)
### Kernel:
- Linux 4.19.71-rt24-v7 + PREEMPT_RT
## Build
```
git clone --recursive https://github.com/zhw618/ewdl-test.git
mkdir -p ewdl-test/build/
cd ewdl-test/build/
cmake -D CMAKE_BUILD_TYPE=Release ..
make
```
## Warning
The executable will configure the EWDL/SV660N drive to operate in **Cyclic Synchronous Position Mode (CSP)**, then it will execute a _sin_ function between +/- 10000 encoder counts.

***Before run it be sure that the motor is free to move between the limits.***

## Run
```
sudo chrt --rr 90 ./idle
```
or
```
sudo chrt --rr 90 ./run
```
