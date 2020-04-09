## Lidar Odometry And Mapping [source](http://wiki.ros.org/loam_velodyne)

This version of the code has been adopted from [here](https://github.com/laboshinl/loam_velodyne)
```
 - The original version of this code in the above link is set to work with velodyne lidar
 - This code in this repo has been modified to be used with Ouster OS_1 lidar, which takes care of the 
 lidar resolution, fov and the frame of reference
```

All sources were taken from [ROS documentation](http://docs.ros.org/indigo/api/loam_velodyne/html/files.html)
Ask questions [here](https://github.com/laboshinl/loam_velodyne/issues/3).

## How to build with catkin

```
$ cd ~/catkin_ws/src/
$ https://github.com/DeepakKarishetti/loam
$ cd ~/catkin_ws
$ catkin_make -DCMAKE_BUILD_TYPE=Release 
$ source ~/catkin_ws/devel/setup.bash
```

## Launch

```
roslaunch loam_velodyne loam_ouster.launch
```

In another terminal play a rosbag file containing the appropriate topic name mentioned in the launch file
Or a lidar can be used in real time to get the range measurements

```
rosbag play <bag_file_name> 
```

```
 - In this example implementation a rosbag file is used and the topic used is /os1_cloud_node/points
 - The registered point cloud is published on the topic name /laser_cloud_surround
 - This can be recorded into a rosbag and can be converted into a pcd format using pcl_ros
 - The pcd files can be visualized using pcl_viewer
```

