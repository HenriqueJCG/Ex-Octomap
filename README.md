# Octomap Exercise
Repository for [octomap tutorial](https://github.com/tejalbarnwal/octomap_tutorial), using Ubuntu 24.04, ROS2 Jazzy LTS and Gazebo Harmonic.

---

First source the setup file: `cd ~/octomap_ws` `colcon build` `source install/setup.bash`

To run use `ros2 launch my_robot_description main.launch.py mode:=teleop` and `ros2 launch octomap_server octomap_mapping.launch.xml`


To save the octomap use `ros2 run octomap_server octomap_saver_node --ros-args -p octomap_path:=(~/octomaps)`