# turtlebot_teleop_joystick

A simple HTML-based joystick teleoperation interface for TurtleBot3 (including Gazebo simulations). This project provides an on-screen joystick that publishes velocity commands (`/cmd_vel`) via a WebSocket bridge using [`rosbridge_suite`](https://github.com/RobotWebTools/rosbridge_suite).

You need to install **rosbridge_suite** for ROS 2 Humble:

```bash
# Update your package index
sudo apt-get update

# Install the rosbridge_suite package for ROS 2 Humble
sudo apt-get install ros-humble-rosbridge-suite
```
## Usage

1. **Launch Your Robot**
    Either bring up your real TurtleBot3 or launch a TurtleBot3 Gazebo simulation.
    For example (on a real robot or running the simulation locally):
    
    ```bash
    export TURTLEBOT3_MODEL=burger
	ros2 launch turtlebot3_bringup robot.launch.py

	```
	
    - Or for Gazebo:
        
        ```bash
        export TURTLEBOT3_MODEL=burger
        ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
        ```
        
2. **Run rosbridge_server**  
    Start the WebSocket server in a separate terminal:
    
    ```bash
    ros2 run rosbridge_server rosbridge_websocket
    ```
    
    By default, this opens a WebSocket on port `9090`.
    
3. **Open the Joystick Page**
    
    Open the provided `index.html` file in your browser (or serve it via a simple HTTP server).
    If rosbridge is on the same machine, set the IP to `localhost` and the port to `9090`.
    Click **Connect**, and once connected, use the on-screen joystick to control your TurtleBot3!

