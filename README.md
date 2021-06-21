# Reboot-Arm.
welcome to my new project in the [Smart Methods](https://www.s-m.com.sa/)

so in the beging i just start using Ubuntu 20.04 and i chosse to start with ROS noetic vision which support Ubuntu 20.04 and i faced an small problem to run the arm so here is the step and commend that i used 
after installing notice and follow the instructions in this website [ROS notice](http://wiki.ros.org/noetic/Installation/Ubuntu)
i stoped 
###  in step 1.3 **set up your key**
i have to install Curl keys by using this command ```sudo apt install curl``` and ```sudo apt update```  just to make sure every thing up to date 

###  set up the environment of **ROS:::** 
i must write this source this script in every bash terminal i use ROS in.
the web shell, which we use to run our commands. By running ls ~/catkin_ws/devel/  we can see that among other files, we have setup.bash and setup.sh:
The main function of these files is to set environment variables used by ROS and by the Gazebo simulator
### Dependencies for building packages
- ***First*** 
to create and manage my own ROS workspaces because there are various tools and requirements that are distributed separately tool that enables you to easily download many source trees for ROS packages with one command --> ```  sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential ```
- ***second*** 
  
  1.`sudo apt install python-rosdep`
ROS provides a simple tool, rosdep, that is used to download and install system dependencies.
ROS packages sometimes require external libraries and tools that must be provided by the operating system. These required libraries and tools are commonly referred to as system dependencies and here we use python package that supports notice visions 

   2.`sudo rosdep init`
to initialize it 

     3.`rosdep update`
The source of rosdep key entries are maintained on rosdistro repository and frequently updated.
### Creat a work space 
now here we have to install the ROS notice vision and create a Work space but first let me explain what catkin is
##### Catkin
  : catkin combines CMake macros and Python scripts to provide some functionality on top of CMake's normal workflow
 >  ### now we are going to use these commend :
 > 1. `sudo apt-get install ros-noetic-catkin`
 > 2. `mkdir -p ~/catkin_ws/src`  > This command is when you don't know whether a directory alredy exists or not
 > 3. `cd ~/catkin_ws/` > change which folder we are in. When using the command
 > 4. `cd ~/catkin_ws/src` 
 > 5.  `catkin_make` > creates directories and runs cmake command for you and convenience tool for building code in a catkin workspace
 > 6.  `cd ~/catkin_ws/src`


