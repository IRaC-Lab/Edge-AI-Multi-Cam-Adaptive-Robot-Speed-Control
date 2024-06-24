# Edge-AI-Multi-Cam-Adaptive-Robot-Speed-Control
 Simulation Implementation for "Edge AI-Driven Multi-Camera System for Adaptive Robot Speed Control in Safety-Critical Environments"

## Packages

### 1. Gazebo ROS Link Attacher (Melodic Devel)
- **Description**: Provides tools for attaching and detaching links in Gazebo simulations.
- **Source**: [gazebo_ros_link_attacher](https://github.com/pal-robotics/gazebo_ros_link_attacher.git)

### 2. Robotiq (Noetic Devel)
- **Description**: ROS packages for controlling Robotiq grippers.
- **Source**: [robotiq](https://github.com/cambel/robotiq.git)

### 3. YOLOv5
- **Description**: Real-time object detection algorithm implemented using PyTorch.
- **Source**: [yolov5](https://github.com/ultralytics/yolov5)

### 4. Realsense ROS (ROS1 Legacy)
- **Description**: Intel Realsense camera integration with ROS.
- **Source**: [realsense-ros](https://github.com/IntelRealSense/realsense-ros/tree/ros1-legacy)

### 5. UR3 (Noetic Devel)
- **Description**: ROS packages for controlling the Universal Robots UR3 robotic arm.
- **Source**: [ur3](https://github.com/cambel/ur3.git)

## How to Use

1. **Clone the repository**:

    ```bash
    cd ~/catkin_ws/src
    git clone https://github.com/IRaC-Lab/Edge-AI-Multi-Cam-Adaptive-Robot-Speed-Control.git
    ```

2. **Build the packages**:

    ```bash
    cd ~/catkin_ws
    catkin_make
    ```

3. **Running Gazebo and MoveIt**:

    ```bash
    roslaunch ur_gripper_gazebo ur_gripper_85_person.launch
    ```
    
    ```bash
    roslaunch ur_gripper_85_moveit_config start_moveit.launch
    ```
    
    ```bash
    rosrun ur_control sim_ur_control.py
    ```
    
3. **Running Operator Detection**: YOLOv5n-seg, Alignment and Distance Measurment

    ```bash
    cd catkin_ws/src/yolov5/segment
    python3 predict.py --conf 0.7
    ```
    
    ```bash
    rosrun realsense2_camera align_depth_to_color.py
    ```
    
    ```bash
    rosrun realsense2_camera depth_distance_seg.py
    ```

## License

Each package within this repository is distributed under its respective license. Please refer to each package's original repository for specific licensing information.
