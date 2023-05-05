# Installation
## Step 1: http://wiki.ros.org/noetic/Installation/Ubuntu
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

sudo apt update
sudo apt install ros-noetic-desktop-full

source /opt/ros/noetic/setup.bash
```
## Step 2: https://clover.coex.tech/en/simulation_native.html
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install build-essential git python3-pip python3-rosdep

# Create a workspace for the simulation
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
# Clone Clover sources:
cd ~/catkin_ws/src
git clone --depth 1 https://github.com/CopterExpress/clover
git clone --depth 1 https://github.com/CopterExpress/ros_led
git clone --depth 1 https://github.com/ethz-asl/mav_comm
# Install all dependencies using rosdep:
cd ~/catkin_ws
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -y
# Install Python dependencies:
sudo /usr/bin/python3 -m pip install -r ~/catkin_ws/src/clover/clover/requirements.txt
```
## Step 3: http://docs.px4.io/main/en/dev_setup/dev_env_linux_ubuntu.html#gazebo-jmavsim-and-nuttx-pixhawk-targets
```
# Get PX4 sources
cd
git clone --recursive --depth 1 --branch v1.12.0 https://github.com/PX4/PX4-Autopilot.git ~/PX4-Autopilot
ln -s ~/PX4-Autopilot ~/catkin_ws/src/
ln -s ~/PX4-Autopilot/Tools/sitl_gazebo ~/catkin_ws/src/
ln -s ~/PX4-Autopilot/mavlink ~/catkin_ws/src/
# Install PX4 prerequisites
cd ~/catkin_ws/src/PX4-Autopilot/Tools/setup
sudo ./ubuntu.sh

pip3 install --user toml

# Add the Clover airframe
ln -s ~/catkin_ws/src/clover/clover_simulation/airframes/* ~/PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/airframes/
# Install geographiclib datasets
sudo /opt/ros/noetic/lib/mavros/install_geographiclib_datasets.sh

# Build the simulator
cd ~/catkin_ws
catkin_make

# Run the simulator
roslaunch clover_simulation simulator.launch
```
## Step 4: https://docs.qgroundcontrol.com/master/en/getting_started/download_and_install.html
```
# Before installing
sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager -y
sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y
sudo apt install libqt5gui5 -y

# Logout and login again to enable the change to user permissions.

# Download 
https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl.AppImage

# Install (and run)
chmod +x ./QGroundControl.AppImage
./QGroundControl.AppImage  (or double click)
```

# 
