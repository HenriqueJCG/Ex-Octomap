# Octomap Exercise
Repository for [octomap tutorial](https://github.com/tejalbarnwal/octomap_tutorial), using Ubuntu 24.04, ROS2 Jazzy LTS and Gazebo Harmonic.

---

# Manual Way

First source the setup file: `cd ~/octomap_ws` `colcon build` `source install/setup.bash`

To run use `ros2 launch my_robot_description main.launch.py mode:=teleop` and `ros2 launch octomap_server octomap_mapping.launch.xml`


To save the octomap use `ros2 run octomap_server octomap_saver_node --ros-args -p octomap_path:=(~/octomaps)`


---

# Demo Way

First open the demo from the *ros_gz/ros_gz_sim_demos/* package: `ros2 launch ros_gz_sim_demos gpu_lidar_bridge.launch.py`

Then, we need to aply a transform  from the robot to the base with a static transform:

`ros2 run tf2_ros static_transform_publisher 0 0 0.1 0 0 0 base_link model_with_lidar/link/gpu_lidar`

Last, we can use the octomap_server to map the /PointCloud2 msgs into octomap


`ros2 run octomap_server octomap_server_node --ros-args -p frame_id:=base_link -r cloud_in:=/lidar/points`