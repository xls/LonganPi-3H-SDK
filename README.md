# LonganPi-3H-SDK
Scripts and blobs for LonganPi 3H image build.
> Tested on Ubuntu 22.04.2 LTS





0. Install some dependencies
```shell
sudo apt update
sudo apt install qemu-user-static gcc-aarch64-linux-gnu mmdebstrap git binfmt-support make build-essential  bison flex make gcc libncurses-dev debian-archive-keyring swig libssl-dev bc python3-setuptools python3-dev
```

_note: mklinux.sh  git patching will fail patching if username and email is unset_
setup git environment if not already set.
Don't forget to set your git user.name and user.email 
```
git config --global user.name "Mona Lisa"
git config --global user.email "Mona.Lisa@email.com"
```
 

1. Build arm-trusted-firmware
```shell
./mkatf.sh
```

2. Build uboot
```shell
./mkuboot.sh
```

3. Build kernel
```shell
./mklinux.sh
```

4. Build rootfs debian

```shell
sudo ./mkrootfs.sh
# or ./mkrootfs-ubuntu.sh
```


Creating a bootable image see wiki [here](https://wiki.sipeed.com/hardware/en/longan/h618/lpi3h/7_develop_mainline.html#Make-a-boot-TF-card-image)
