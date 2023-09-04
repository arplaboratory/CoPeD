# CoPeD - Advancing Multi-Robot Collaborative Perception: A Comprehensive Dataset in Real-World Environments

## Data Link
[Google Drive Link to Dataset](https://t.ly/zy2vC) 

## Description
CoPeD is a multi-robot collaborative perception dataset that contains indoor/outdoor sequence collected by multiple air/ground robots. This dataset features a variety of sensors including stereo RGB cameras, infrared cameras, IMUs, GPS, and LiDARs. The dataset is collected in real-world environments with various lighting conditions and weather conditions. 

## Specifications of Ground/Aerial Robot ROS Sensor Messages

### Ground Robot

| Topic Name                                     | Message Type                       | Message Rate | Description          |
|------------------------------------------------|------------------------------------|--------------|----------------------|
| /forward/color/image_rect_color/compressed     | sensor_msgs/CompressedImage       | 30 Hz       | RGB image            |
| /forward/infra1/image_rect_raw/compressed      | sensor_msgs/CompressedImage       | 30 Hz       | Left IR image        |
| /forward/infra2/image_rect_raw/compressed      | sensor_msgs/CompressedImage       | 30 Hz       | Right IR image       |
| /imu/data                                      | sensor_msgs/Imu                   | 125 Hz      | IMU data             |
| /stereo_left/image_rect_color/compressed       | sensor_msgs/CompressedImage       | 30 Hz       | Left RGB image       |
| /stereo_right/image_rect_color/compressed      | sensor_msgs/CompressedImage       | 30 Hz       | Right RGB image      |
| /gps                                           | sensor_msgs/NavSatFix             | 1 Hz        | GPS data             |
| /lidar_points                                  | sensor_msgs/PointCloud2           | 10 Hz       | Point cloud data     |

### Aerial Robot

| Topic Name                                     | Message Type                       | Message Rate | Description          |
|------------------------------------------------|------------------------------------|--------------|----------------------|
| /cam1/color/image_raw/compressed               | sensor_msgs/CompressedImage       | 30 Hz       | RGB image            |
| /cam1/infra1/image_rect_raw/compressed         | sensor_msgs/CompressedImage       | 30 Hz       | Left IR image        |
| /cam1/infra2/image_rect_raw/compressed         | sensor_msgs/CompressedImage       | 30 Hz       | Right IR image       |
| /main_camera/image_raw/compressed              | sensor_msgs/CompressedImage       | 30 Hz       | Downward RGB image   |
| /mavros/global_position/raw/fix                | sensor_msgs/NavSatFix             | 8 Hz        | GPS data             |
| /cam1/imu                                      | sensor_msgs/Imu                   | 200 Hz      | IMU data             |

## Calibration
```
├── ptah
│   └── extrinsics.yaml
├── race1
│   └── camchain-imucam.yaml
├── race5
│   └── camchain-imucam.yaml
├── wanda
│   ├── 19509600.yaml
│   ├── 19509635.yaml
│   ├── extrinsics.yaml
│   └── tag_bundle_wanda.yaml
└── wilbur
    ├── 19504539.yaml
    ├── 19509631.yaml
    ├── extrinsics.yaml
    └── tag_bundle_wilbur.yaml
```
For aerial robots "race1" and "race5", the camera intrinsics and extrinsics with respect to realsesne IMU are provided in "camchain-imucam.yaml". 

For ground robots "wanda", "wilbur" and "ptah", the extrinsics of robot frames with respect to "base_link" are provided in "extrinsics.yaml". The stereo RGB camera intrinsics are provided in "19509600.yaml" and "19509635.yaml" for "wanda" and "19504539.yaml" and "19509631.yaml" for "wilbur". The AprilTag bundle calibration of "wilbur" and "wanda" are provided in "tag_bundle_wanda.yaml" and "tag_bundle_wilbur.yaml".

The "tag_bundle_joint" of "wilbur" and "wanda" are tag 0 and tag 8.
The "base_link" of "wanda", "wilbur" and "wanda" are the center footprint of the robot, which is the projection of the center of the robot on the ground.

