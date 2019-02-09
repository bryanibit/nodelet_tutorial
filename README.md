## Introduction

The goal is to test nodelet as an example. This will build a nodelet which subscribes */Plus3/in* and publishes */Plus3/out*. For finishing the process, I remap subscribed topic to */foo*.

## Usage 1

```
catkin_make
rostopic pub /foo std_msgs/Float64 2.5 -r 10
roslaunch nodelet_tutorial_math plus.launch
rostopic echo /Plus3/out
```

## Usage 2

[refer to the link](http://library.isr.ist.utl.pt/docs/roswiki/nodelet(2f)Tutorials(2f)Running(20)a(20)nodelet.html)

```
roscore
# bring up a manager
rosrun nodelet nodelet manager __name:=nodelet_manager
# launch the nodelet
rosrun nodelet nodelet load nodelet_tutorial_math/Plus nodelet_manager __name:=nodelet1 nodelet1/in:=foo _value:=2.5
rostopic pub /foo std_msgs/Float64 5.0 -r 10
rostopic echo /nodelet1/out
```
