# Octomap Exercise
Repository for the [octomap tutorial](https://github.com/tejalbarnwal/octomap_tutorial) on how to create an octomap, using Ubuntu 24.04, ROS2 Jazzy LTS and Gazebo Harmonic.

---

First source the setup file: `cd ~/octomap_ws` `colcon build` `source install/setup.bash`

To run use `ros2 launch my_robot_description main.launch.py mode:=teleop` and to create the octomap use `ros2 run octomap_server octomap_server_node --ros-args -p frame_id:=base_link -r cloud_in:=/lidar/points`


To save the octomap use `ros2 run octomap_server octomap_saver_node --ros-args -p octomap_path:=/home/henrique/octomaps/map.bt` (Change path to where you want to save and the name of the map)

And `octovis /home/henrique/octomaps/my_map.bt` to visualize the created octomap. (Change path to your map location)

---

**Youtube Video:** [https://youtu.be/-V0-M3m5fdM](https://youtu.be/-V0-M3m5fdM)