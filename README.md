## Move Arctos with Scratch3


**WORK IN PROGRESS**

![scratch3-ros](https://github.com/ArctosRobotics/scratch3-ros/blob/master/Arctos%20ROS%20Scratch.jpg)

### Run from source

```bash
sudo apt install npm # Tested with versions 6.4.0 and 10.12.0
mkdir Scratch; cd Scratch
git clone https://github.com/Affonso-Gui/scratch-vm.git
git clone https://github.com/Affonso-Gui/scratch-gui.git

cd scratch-vm
npm install
npm link

cd ../scratch-gui
npm install
npm link scratch-vm
npm start
```

## Load Arctos Pick and place demo 

Reqirements: 
Arctos GUI - https://github.com/ArctosRobotics/arctosgui
Rosbridge - http://wiki.ros.org/rosbridge_suite
```
cd arctosgui 
./run.sh 
cd
cd Scratch/scratch-gui 
npm start 

In browser:
localhost:8601
File > Load from your computer
Arctos.sb3
```
Install and run rosbridge: 
```
sudo apt-get install ros-melodic-rosbridge-server

roslaunch rosbridge_server rosbridge_websocket.launch
```
Then in Scratch find last block called ROS localhost, then click on the ! icon and as Master URI: type localhost and press OK 
You should get Connected status. Otherwise check if the rosbridge server is properly installed and run. 



### Basic Usage
![scratch3-ros](https://github.com/ArctosRobotics/scratch3-ros/blob/master/Scratch%20blocks.jpg)

Basic publishers on /ui_command topic. Same one which works with Arctos GUI to move the robot. 
To make new predefined pose, move the robot with gui, make "Get message from" block and use /joint_states or /transformed_tf 
to set the new pose data. Those can be pasted into "Set joint data to" block to make new custom pose. 

