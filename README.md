# Starfive ARM Linux for Gem5 FS Emulation
> **ATTENTION:** We highly recommend you use Ubuntu-18.04 with gcc-7 to build the kernel. gcc-8 and later version does build the kernel successfully, but gem5 will refuse to boot!!

## 1. Prerequisites
if you use docker, run the following command:
```bash
apt update && apt upgrade && apt install build-essential make cmake ibncurses5-dev libncursesw5-dev gcc-arm-linux-gnueabihf gcc-aarch64-linux-gnu device-tree-compiler && unminimize
```
Otherwise:
```bash
sudo apt update && sudo apt upgrade && sudo apt install build-essential make cmake ibncurses5-dev libncursesw5-dev gcc-arm-linux-gnueabihf gcc-aarch64-linux-gnu device-tree-compiler
```

## 2. Kernel build
**Before building the kernel, make sure you are currently on branch v4.15**
```bash
cp arch/arm64/configs/starfive_gem5_numa_defconfig .config
make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- -j 32
```
**You can enjoy a cup of coffee while waiting. When it finishes successfully, newly built kernel can be found under the current directory called `vmlinux`**
