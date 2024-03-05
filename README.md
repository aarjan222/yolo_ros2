## This package is the ros2 package which does object detection in real world. object like car, human, bike, sticks, buildings, tree, road.

## For running the camera driver
```shell
ros2 run v4l2_camera v4l2_camera_node
```

## Build the package
```shell
colcon build --symlink-install
source install/setup.bash
```

## RUN the yolov8 ros2 object detector node
```shell
ros2 run yolobot_recognition yolov8_ros2_pt.py  
```

## You should see output like this in your terminal if everything is working properly
```shell
0: 480x640 1 Road, 6.2ms
Speed: 1.2ms preprocess, 6.2ms inference, 0.6ms postprocess per image at shape (1, 3, 480, 640)

0: 480x640 1 Road, 6.2ms
Speed: 1.1ms preprocess, 6.2ms inference, 0.6ms postprocess per image at shape (1, 3, 480, 640)
```

## output of listed topic:
```shell
$ ros2 topic list
/Yolov8_inference
/camera_info
/image_raw
/image_raw/compressed
/image_raw/compressedDepth
/image_raw/theora
/inference_result
/parameter_events
/rosout
```

## See results
- Open rviz2 
- See under By topic
    /inference_result
- Click on image
We see image with prediction with boundary boxes.

```shell
ros2 run yolobot_recognition yolov8_ros2_subscriber.py 
```

Subscribes the /yolov8_ineference type message and from that msg tries to publish only bb no class in the image.

- See under by topic 
 /inference_result_cv2
- Click on Image


