# learning_docker_ros_moveit
## Settings
1. Run
Example command to run container from this image.  
Make sure to replace **your_container_name** and **your/local/directory(not yet exist)** to your own information.
<pre>  
docker run -it --name=<b>your_containr_name</b> -p 9090:9090 -p 27017:27017 -p 13389:3389 -v <b>your/local/directory(not yet exist)</b>:/root/ws_moveit takumakawakami/tk_ros_moveit_xrdp:version2
</pre>  
Example:  
<pre>
docker run -it --name=ros_moveit_dt -p 9090:9090 -p 27017:27017 -p 13389:3389 -v C:\Users\tak-mahal\Documents\docker\ws_moveit:/root/ws_moveit takumakawakami/tk_ros_moveit_xrdp:version2
</pre>
2. Start  xrdp
`/etc/init.d/xrdp stop`  
`/etc/init.d/xrdp start`  

3. Log in with RDP
Example address when you run your container on your local machine  
localhost:13389
* ID: root
* Passwd:moveit

## Next Step
http://docs.ros.org/melodic/api/moveit_tutorials/html/doc/getting_started/getting_started.html  
`cd ~/ws_moveit`  
`mkdir src`  
`git clone https://github.com/ros-planning/moveit_tutorials.git -b melodic-devel`  
`cd ~/ws_moveit`  
`catkin config --extend /opt/ros/melodic --cmake-args -DCMAKE_BUILD_TYPE=Release`  
`catkin build`  
