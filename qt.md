(https://github.com/PhysicsX/QTonRaspberryPi)
# QTonRaspberryPi

Youtube video:

[![Youtube video link](https://img.youtube.com/vi/TmtN3Rmx9Rk/0.jpg)](//www.youtube.com/watch?v=TmtN3Rmx9Rk?t=0s "ulas dikme")

Qt Configuration on raspberry pi

# Ubuntu History

```bash
  sudo apt-get update
  sudo apt-get upgrade
  ping 192.168.16.25
  sudo bash
  apt-get install gcc git bison python gperf pkg-config
  apt install make
  apt install libclang-dev
  apt install build-essential
  mkdir /opt/qt5pi
  chown ulas:ulas /opt/qt5pi
  cd /opt/qt5pi/
  
  wget https://releases.linaro.org/components/toolchain/binaries/latest-7/arm-linux-gnueabihf/gcc-linaro-7.5.0-2019.12-x86_64_arm-linux-gnueabihf.tar.xz
  tar xf gcc-linaro-7.5.0-2019.12-x86_64_arm-linux-gnueabihf.tar.xz 
  export PATH=$PATH:/opt/qt5pi/gcc-linaro-7.5.0-2019.12-x86_64_arm-linux-gnueabihf/bin
  nano ~/.bashrc
  
  wget https://download.qt.io/official_releases/qt/5.15/5.15.2/single/qt-everywhere-src-5.15.2.tar.xz
  tar xf qt-everywhere-src-5.15.2.tar.xz 
  cat qt-everywhere-src-5.15.2/qtbase/mkspecs/linux-arm-gnueabi-g++/qmake.conf
  
  ping 192.168.16.25
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/usr/include sysroot/usr
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/lib sysroot
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/usr/lib sysroot/usr 
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/opt/vc sysroot/opt
  ls sysroot/usr/lib/arm-linux-gnueabihf/libEGL.so.1.1.0
  mv sysroot/usr/lib/arm-linux-gnueabihf/libEGL.so.1.1.0 sysroot/usr/lib/arm-linux-gnueabihf/libEGL.so.1.1.0_backup
  ln -s sysroot/opt/vc/lib/libEGL.so sysroot/usr/lib/arm-linux-gnueabihf/libEGL.so.1.1.0
  mv sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0 sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0_backup
  ln -s sysroot/opt/vc/lib/libGLESv2.so sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0
  mv sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0 sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0_backup
  ls sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0
  ln -s sysroot/opt/vc/lib/libGLESv2.so sysroot/usr/lib/arm-linux-gnueabihf/libGLESv2.so.2.1.0
  ln -s sysroot/opt/vc/lib/libEGL.so sysroot/opt/vc/lib/libEGL.so.1
  ln -s sysroot/opt/vc/lib/libGLESv2.so sysroot/opt/vc/lib/libGLESv2.so.2
  wget https://raw.githubusercontent.com/riscv/riscv-poky/master/scripts/sysroot-relativelinks.py
  chmod +x sysroot-relativelinks.py 
  ./sysroot-relativelinks.py sysroot
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/lib sysroot 
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/usr/include sysroot/usr
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/usr/lib sysroot/usr
  rsync -avz --rsync-path="sudo rsync" pi@192.168.16.25:/opt/vc sysroot/opt/
  ./sysroot-relativelinks.py sysroot
  mkdir qt5build
  cd qt5build/
  ../qt-everywhere-src-5.15.2/configure -opengl es2 -device linux-rasp-pi4-v3d-g++ -device-option CROSS_COMPILE=/opt/qt5pi/gcc-linaro-7.5.0-2019.12-x86_64_arm-linux-gnueabihf/bin/arm-linux-gnueabihf- -sysroot /opt/qt5pi/sysroot -prefix /usr/local/qt5pi -opensource -confirm-license -skip qtscript -skip qtwayland -skip qtdatavis3d -nomake examples -make libs -pkg-config -no-use-gold-linker -v
  make -j8
  make install
  cd /opt/qt5pi/
  rsync -avz --rsync-path="sudo rsync" sysroot/usr/local/qt5pi pi@192.168.16.25:/usr/local
```

# Raspberry pi history

```bash
sudo vi /etc/apt/sources.list
sudo apt update
sudo apt full-upgrade
sudo reboot
sudo rpi-update
sudo reboot

sudo apt-get build-dep qt5-qmake
sudo apt-get build-dep libqt5webengine-data

sudo apt-get install libboost1.58-all-dev libudev-dev libinput-dev libts-dev libmtdev-dev libjpeg-dev libfontconfig1-dev 
sudo apt-get install libssl-dev libdbus-1-dev libglib2.0-dev libxkbcommon-dev libegl1-mesa-dev libgbm-dev libgles2-mesa-dev mesa-common-dev
sudo apt-get install libasound2-dev libpulse-dev gstreamer1.0-omx libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev  gstreamer1.0-alsa
sudo apt-get install libvpx-dev libsrtp0-dev libsnappy-dev libnss3-dev
sudo apt-get install "^libxcb.*"
sudo apt-get install flex bison libxslt-dev ruby gperf libbz2-dev libcups2-dev libatkmm-1.6-dev libxi6 libxcomposite1
sudo apt-get install libfreetype6-dev libicu-dev libsqlite3-dev libxslt1-dev libavcodec-dev libavformat-dev libswscale-dev 
sudo apt-get install libgstreamer0.10-dev gstreamer-tools libraspberrypi-dev libx11-dev libglib2.0-dev 
sudo apt-get install freetds-dev libsqlite0-dev libpq-dev libiodbc2-dev firebird-dev libjpeg9-dev libgst-dev libxext-dev libxcb1 libxcb1-dev libx11-xcb1 
sudo apt-get install libx11-xcb-dev libxcb-keysyms1 libxcb-keysyms1-dev libxcb-image0 libxcb-image0-dev libxcb-shm0 libxcb-shm0-dev libxcb-icccm4 libxcb-icccm4-dev 
sudo apt-get install libxcb-sync1 libxcb-sync-dev libxcb-render-util0 libxcb-render-util0-dev libxcb-xfixes0-dev libxrender-dev libxcb-shape0-dev libxcb-randr0-dev 
sudo apt-get install libxcb-glx0-dev libxi-dev libdrm-dev libssl-dev libxcb-xinerama0 libxcb-xinerama0-dev
sudo apt-get install libatspi-dev libssl-dev libxcursor-dev libxcomposite-dev libxdamage-dev libfontconfig1-dev 
sudo apt-get install libxss-dev libxtst-dev libpci-dev libcap-dev libsrtp0-dev libxrandr-dev libnss3-dev libdirectfb-dev libaudio-dev


sudo mkdir /usr/local/qt5pi
sudo chown pi:pi /usr/local/qt5pi

```

## Qt creator enable ssh deployment (on Raspberry Pi)
```bash
export QT_QPA_PLATFOMRTHEME=qt5ct
export DISPLAY=:0.0
export XAUTHORITY=/home/pi/.Xauthrity
export XDG_SESSION_TYPE=x11
