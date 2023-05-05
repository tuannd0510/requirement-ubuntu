# Installation
1. download .run file : qt online installer
```
# Permissions / Allow exe
chmod a+x qt-....
# 
./qt-... --mirror http://www.nic.funet.fi/pub/mirrors/download.qt-project.org
```

## Libs

### LibVLC
1. requirements
- cmake: https://cgold.readthedocs.io/en/latest/first-step/installation.html
- sudo apt-get install qtdeclarative5-dev libvlccore-dev libvlc-dev
2. installation
```
git clone git@github.com:vlc-qt/vlc-qt.git
cd vlc-qt
mkdir build
cd build
export CMAKE_PREFIX_PATH=<path-to-qt>/Qt/5.15.2/gcc_64:$CMAKE_PREFIX_PATH
cmake .. -DCMAKE_BUILD_TYPE=Debug
make -j8
sudo make install
```
### qtmqtt

```
git clone https://github.com/qt/qtmqtt.git --branch 5.15.2
cd qtmqtt
sudo ~/Qt/5.15.2/gcc_64/bin/qmake
sudo make
sudo make install
```
