# Settings
## Docker Run  
Example command to run container from this image.  
Make sure to replace **your_container_name** and **your/local/directory(not yet exist)** to your own information.
<pre>  
docker run -it --name=<b>your_containr_name</b> -p 9090:9090 -p 27017:27017 -p 13389:3389 -v <b>your/local/directory(not yet exist)</b>:/root/ws_moveit takumakawakami/tk_ros_moveit_xrdp:version2
</pre>  
Example:  
<pre>
docker run -it --name=ros_moveit_dt -p 9090:9090 -p 27017:27017 -p 13389:3389 -v C:\Users\tak-mahal\Documents\docker\ws_moveit:/root/ws_moveit takumakawakami/tk_ros_moveit_xrdp:version2
</pre>
## Start xrdp  
`/etc/init.d/xrdp stop`  
`/etc/init.d/xrdp start`  

## Log in with RDP  
Example address when you run your container on your local machine  
localhost:13389
* ID: root
* Passwd:moveit

# Moveit Tutorial
http://docs.ros.org/melodic/api/moveit_tutorials/html/doc/getting_started/getting_started.html 
## Getting Started
### Download Example Package
 
`cd ~/ws_moveit`  
`mkdir src`  
`git clone https://github.com/ros-planning/moveit_tutorials.git -b melodic-devel`  
### Build your Catkin Workspace
`cd ~/ws_moveit`  
`catkin config --extend /opt/ros/melodic --cmake-args -DCMAKE_BUILD_TYPE=Release`  
`catkin build`  
## Moveit Setup Assistant
`roslaunch moveit_setup_assistant setup_assistant.launch`
## Move Group Python Interface
`roslaunch panda_moveit_config demo.launch`
# Next Step
## RosBridge
`roslaunch rosbridge_server rosbridge_websocket.launch`
