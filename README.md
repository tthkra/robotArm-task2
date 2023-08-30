# robotArm-task2

to run a simulated robot arm in ROS, you can follow thses instructions:


assuming you already have your Ubntu and ROS installed, open the terminal and run the following commands:


### create a ROS workspace
create a new directory for your ROS workspace
``` mkdir -p ~/catkin_ws/src ```
go to the directory 
``` cd ~/catkin_ws/src ```
configure your workspace
``` catkin_make ```

### clone required packages
go to src folder
``` cd ~/catkin_ws/src ```
clone the required packages, you can use arduino_robot_arm provided by @smart-methods
``` git clone https://github.com/smart-methods/arduino_robot_arm.git ```

### install dependencies
``` cd ~/catkin_ws ```
``` rosdep install --from-paths src --ignore-src -r -y ```
for ROS melodic distro (you can replace melodic with the one youre working with)
``` sudo apt-get install ros-melodic-moveit ```
``` sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui ```
``` sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher ```
``` sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control ```

### open and edit .bashrc file
open .bashrc file
``` sudo nano ~/.bashrc ```
add the following line to the end of file, and replace username with your own username
``` source /home/username/catkin_ws/devel/setup.bash ```
press Ctrl+O, Enter, Ctrl+X
update .bashrc file
``` source ~/catkin_ws/devel/setup.bash ```

### launch the robot arm
finally, run this command to launch the robot arm 
``` roslaunch robot_arm_pkg check_motors.launch ```
this will launch the robot arm on RViz, a 3D visualization tool for ROS.
you can now manipulate and control the robot arm 

### result
![](Screenshot.png)




