## Introduction

The goal is to test nodelet as an example. This will build a nodelet which subscribes */Plus3/in* and publishes */Plus3/out*. For finishing the process, I remap subscribed topic to */foo*.

## Usage

```
catkin_make
rostopic pub /foo std_msgs/Float64 2.5 -r 10
roslaunch nodelet_tutorial_math plus.launch
rostopic echo /Plus3/out
```
