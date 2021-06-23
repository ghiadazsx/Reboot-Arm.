# Reboot-Arm.
Welcome to my new project in the [Smart Methods](https://www.s-m.com.sa/)

In the beginning, I start using Ubuntu 20.04 and worked with ROS noetic vision; I faced a tiny problems to run the arm, so here is the step and commend that I used 
after installing notice and follow the instructions on this website [ROS notice](http://wiki.ros.org/noetic/Installation/Ubuntu)

###  you might stopped In step 1.3 **set up your key**
you need to install Curl keys by using these command ```sudo apt install curl``` and ```sudo apt update``` to make sure everything up to date 

###  Set up the environment of **ROS:::** 
You must write this source script in every bash terminal you use ROS in.
The web shell, which we use to run our commands By running ls ~/catkin_ws/devel/ we can see that among other files, we have setup.bash and setup.sh:
The main function of these files is to set environment variables used by ROS and by the Gazebo simulator
### Dependencies for building packages
- ***First*** 
to create and manage your own ROS workspaces because there are various tools and requirements that are distributed separately tool that enables you to easily download many source trees for ROS packages with one command --> ```  sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential ```
- ***Second*** 

  1.`sudo apt install python-rosdep`
  
     ROS provides a simple tool, rosdep, that is used to download and install system dependencies.
   ROS packages sometimes require external libraries and tools that must be provided by the operating system. These required libraries and tools are commonly    referred to as system dependencies and here we use python package that supports notice visions 

   2.`sudo rosdep init`
   
  to initialize it 

  3.`rosdep update`
      The source of rosdep key entries are maintained on rosdistro repository and frequently updated.
### Creat a work space ⚡️
Here we have to install some tools from notice vision to launch the arm 🦾 and also create a workspace called catkin but first let me explain what catkin is
##### Catkin
  : catkin combines CMake macros and Python scripts to provide some functionality on top of CMake's normal workflow
 >  ### now we are going to use these commend :
 > 1. `sudo apt-get install ros-noetic-catkin` > to creat workspaces support notice vision 
 > 2. `mkdir -p ~/catkin_ws/src`  > This command is when you don't know whether a directory alredy exists or not
 > 3. `cd ~/catkin_ws/` > change which folder we are in When using the command
 > 4. `cd ~/catkin_ws/src` > change catkin workspace to src folder 
 > 5.  `catkin_make` > creates directories and runs cmake command for you and convenience tool for building code in a catkin workspace
 > 6.  `cd ~/catkin_ws/src`> let any command in this directories
 ### install the package of the Arm 
We need to install the robot arm package from [Smart Method github](https://github.com/smart-methods/arduino_robot_arm.git ) to work on and actually i faced the problem robot publisher state and to solve the problem i'll explain it later on but first donig these commend which’s 

`git clone https://github.com/smart-methods/arduino_robot_arm.git ` 

`cd ~/catkin_ws`

`rosdep install --from-paths src --ignore-src -r -y`

`sudo apt-get install ros-noetic-moveit`

`sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui`

`sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher`

`sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control`

`sudo nano ~/.bashrc`

*go to the end of file*
`source /home/ghiada/catkin_wrksps/devel/setup.bash`
*then to get back to the terminal press*
ctrl + o
### Before lunch the robot arm to avoid the state publisher 
1. Go to compin joint values in motor.lunch file 
6. Change the `type` to `robot_state_publisher`
7. ![Capture](https://user-images.githubusercontent.com/40144145/123087536-56cfae00-d42d-11eb-86c4-edfb7dc22912.PNG)

### Congratulations you almost finished ✅ 
open the terminal write this command down  
`roslaunch robot_arm_pkg check_motors.launch`
# Launching the arm 🦾🚀
![arm](https://user-images.githubusercontent.com/40144145/122835752-a319d180-d2f9-11eb-90ac-8ab68d2d1020.PNG)
## Base joint 
![arm_base_joint](https://user-images.githubusercontent.com/40144145/122843017-242b9580-d307-11eb-9c7a-b2fb04a90798.png)
## Shoulder 
![untitled2](https://user-images.githubusercontent.com/40144145/122843403-09a5ec00-d308-11eb-95d8-ce39d49599a8.png)
## Elbow 
![untitled3](https://user-images.githubusercontent.com/40144145/122843546-60132a80-d308-11eb-806a-73f4cb5d70b7.png)
## Wrist 
![untitled4](https://user-images.githubusercontent.com/40144145/122843560-6a352900-d308-11eb-90c8-19c1965e2e2f.png)

