# Drone Simulation using Gazebo11
<mark>How to simulate your drone in Gazebo classic</mark> <br>
Go to the terminal (Ctrl + Alt + T)

## Terminal 1
Run MAVProxy
```sh
cd ardupilot/ArduCopter
sim_vehicle.py -v ArduCopter -f gazebo-iris --console
```

## Terminal 2
Run Gazebo and load Iris Drone model
```sh
gazebo --verbose ~/ardupilot_gazebo/worlds/iris_arducopter_runway.world
```
Dont forget to check Connection status at console
![drone](s1.png)
Add the repository to your sources list.

## Terminal 3
run MAVROS Console
```sh
ros2 run mavros mavros_node
```
or
```sh
ros2 run mavros mavros_node --ros-args -p fcu_url:=udp://127.0.0.1:14550@14550
```
![mavros](s2.png)

## check ros2 topic connection
```sh
ros2 topic list
```
## simulate drone
to simulate drone goto MAVProxy console and type the following command
```sh
mode guided
arm throttle
takeoff <altitude_in_meters>
rtl
land
```
![table of simulation](s3.png)
