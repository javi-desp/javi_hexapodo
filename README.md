# H-Robix

H-Robix is a project, consisted in designing, building and programming an hexapod in ROS, with dinamixel servomotors.


![photo_2022-06-16_17-32-17](https://user-images.githubusercontent.com/65245295/195049259-039b3ba3-06bd-4a9c-95d8-c9cb65a84974.png)


## Software scheme

The objective of this project was the remote control of a hexapod, for this reason it was decided to use a cheap computer such as the Raspberry pi to make the connection between the drivers of the motors, sensors and ROS, in this way the calculation of the kinematics and other processes would be carried out on an external computer, where the movement could be visualised in real time with RVIZ. For these reasons, controlling and programming can be subdivided into two parts:

Local control -- where the hexapod publishes the position of each leg and receives the command positions (in XY) 

Remote control -- In this layer the external PC gets info of current position of the hexapod and perform kinematics and gait movement in order to calcule the trajectory, in addition to offering the posibility of display a RViz window where the robot poses in urdf are shown. 


## Local control

The following packages will be needed in this layer: h_robix_sh_codes, h_robix_control, h_robix_description. For this reason the required ROs packet organization will be the next:

```
Catkin_ws
├── src
│   ├── h_robix_control
│   ├── h_robix_description
│   ├── h_robix_sh_codes
├── devel
├── logs
└── build
```

## Remote control

The following packages will be needed in this layer: h_robix_description, h_robix_movement, h_robix_gazebo, rqt_virtual_joystick. Having the next ROS packet organization:

```
Catkin_ws
├── src
│   ├── h_robix_description
│   ├── h_robix_gazebo
│   ├── h_robix_movement
│   ├── rqt_virtual_joystick
├── devel
├── logs
└── build
```


## Video demonstration tripod gait  
https://user-images.githubusercontent.com/65245295/195037681-7bfc925a-f934-4565-9218-098b3da9bce3.mp4


