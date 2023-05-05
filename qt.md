# Installation
1. download .run file : qt online installer
```
# Permissions / Allow exe
chmod a+x qt-....
# 
./qt-... --mirror http://www.nic.funet.fi/pub/mirrors/download.qt-project.org
```

## Libs
1. VLC
### requirements
- cmake: https://cgold.readthedocs.io/en/latest/first-step/installation.html
- 
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

2. mqtt
```
git clone https://github.com/qt/qtmqtt.git --branch 5.15.2
cd qtmqtt
sudo ~/Qt/5.15.2/gcc_64/bin/qmake
sudo make
sudo make install
```
