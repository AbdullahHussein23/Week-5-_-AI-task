# Week-5-_-AI-task

1- لتثبيت ال (gazebo) : sudo apt install ros-humble-gazebo-

2- نثبت ال (cartographer) عشان يسوي لنا المحاكاة و الخريطة :

sudo apt install ros-humble-cartographer

&

sudo apt install ros-humble-cartographer-ros

3-نثبت ال (navigation2) : 

sudo apt install ros-humble-navigation2

&

sudo apt install ros-humble-nav2-bringup

4- لتثبيت ال ( Turtlebot3 package) :

نسوي setup لل (ros humble) :  source /opt/ros/humble/setup.bash

نسوي ملف جديد لل ( turtlebot3) :  mkdir -p ~/turtlebot3_ws/src

ندخل الملف : cd ~/turtlebot3_ws/src/


بعدها نحمل الثلاثة (repositories) : 

git clone -b humble https://github.com/ROBOTIS-GIT/DynamixelSDK.git

git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git

git clone -b humble https://github.com/ROBOTIS-GIT/turtlebot3.git

نثبت (paython colcon) : sudo apt install python3-colcon-common-extensions

بعدها : cd ~/turtlebot3_ws

بعدها : colcon build --symlink-install

بعدها نحط الكود التالي في ملف ال bashrc بحيث كل مره نشغل ال terminal نقدر نشتغل على ال turtlebot بشكل مباشر : echo 'source ~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc

بعدها : source ~/.bashrc

5-نسوي ( Environment Configuration ) : 

echo 'export ROS_DOMAIN_ID=30 #TURTLEBOT3' >> ~/.bashrc

echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc

echo 'source /opt/ros/humble/setup.bash' >> ~/.bashrc

source ~/.bashrc

6-نحدد الموديل حل ال (turtlebot ) اللي هو البرجر: export TURTLEBOT3_MODEL=burger

7- نشغل turtlebot3 gazebo ونشغل ال launch file حقها : ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

8-نشغل ال ( slam node) عشتن الخريطة : 
export TURTLEBOT3_MODEL=burger 

&

ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True

9-لتحديد الموديل والتحكم في حركته :

export TURTLEBOT3_MODEL=burger

&

ros2 run turtlebot3_teleop teleop_keyboard

10- لتحميل الخريطة: ros2 run nav2_map_server map_saver_cli -f ~/map


