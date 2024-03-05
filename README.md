# unet_studio

```
module load pytorch
module load cuda/11.8

conda create --name unetbv   : /ihome/tibrahim/hej24/.conda/envs/unetbv
source activate unetbv

wget https://download.pytorch.org/libtorch/nightly/cpu/libtorch-shared-with-deps-latest.zip
unzip libtorch-shared-with-deps-latest.zip
```

```
./unet_studio: error while loading shared libraries: libQt6Widgets.so.6: cannot open shared object file: No such file or directory

(unetbv) [hej24@login0 libtorch]$ dpkg --print-architecture
amd64
```
check : https://packages.debian.org/sid/amd64/libqt6widgets6/download
```
wget http://ftp.us.debian.org/debian/pool/main/q/qt6-base/libqt6widgets6_6.4.2+dfsg-21_amd64.deb
mkdir qt6
dpkg -x libqt6widgets6_6.4.2+dfsg-21_amd64.deb qt6/

export wmh_seg_home="/ihome/tibrahim/jil202/wmh_seg"
export PATH="/ihome/tibrahim/hej24/qt6:$PATH"


```

# gpn local
```
wget https://github.com/frankyeh/UNet-Studio/releases/download/2023.04.17/unet_studio_ubuntu2204.zip

./unet_studio: error while loading shared libraries: libQt6Widgets.so.6: cannot open shared object file: No such file or directory
sudo apt install qt6-base-dev
    E: Unable to locate package qt6-base-dev
sudo apt update && sudo apt upgrade
    E: The repository 'https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64  InRelease' is no longer signed.


sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub
sudo apt update && sudo apt upgrade
    Errors were encountered while processing:
     /tmp/apt-dpkg-install-NZHKp8/224-nvidia-compute-utils-525_525.147.05-0ubuntu1_amd64.deb
    E: Sub-process /usr/bin/dpkg returned an error code (1)
sudo dpkg --configure -a
sudo apt update && sudo apt upgrade

$ apt search qt6-base
    Sorting... Done
    Full Text Search... Done

$ lsb_release -a
      No LSB modules are available.
      Distributor ID:	Ubuntu
      Description:	Ubuntu 20.04.6 LTS
      Release:	20.04
      Codename:	focal

```



https://jumpcloud.com/blog/how-to-upgrade-ubuntu-20-04-to-ubuntu-22-04
```
sudo apt update && sudo apt upgrade
sudo reboot
sudo apt install update-manager-core

```


# M1 local
docker pull --platform linux/x86_64 dsistudio/unetstudio
docker run -i -t --entrypoint='/bin/bash' --rm --security-opt=apparmor:unconfined -v /path_local:/path_in_docker docker-image



https://viz.crc.pitt.edu/auth/ssh

docker pull dsistudio/unetstudio:latest
