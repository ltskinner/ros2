# Commands

## ROS Commands

### ros2 run - launch and executable from a package

`ros2 run <package_name> <executable_name>`

#### remapping - basically reassign the name of one thing to another

`ros2 run some_package some_ros_executable --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel`

here, map turtle1s /cmd_vel topic onto turtle2s /cmd_vel topic

### ros2 node

#### `ros2 node list` - list all currently running nodes

#### `ros2 node info` - get list of subscribers, publishers, serivces, and actions

`ros2 node info <node_name>`

### ros2 topic

### `ros2 topic list -t` - list all topics as well as topic type

### `ros2 topic echo <topic_name>` - see data being published on a topic

So little early on tidbit here - echo spawns a node that subscribes to that topic and echos it to terminal

### `ros2 topic info <topic_name>` - more of like metadata on topic, instead of literal data

### `ros2 topic pub <topic_name> <msg_type> '<args>'` - publish message

Ok this is super disrespectful actually. e.g.

```bash
# Note, the args string needs to be YAML, tho this appears to be json
ros2 topic pub --once /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.8}}"
```

#### Helpful params

- `--once` just publish this once and only once
- `--rate <1>` do some number of Hz (once a sec i reckon)

### `ros2 topic hz <topic>` - see the rate at which data is being published

## ros2 service

### `ros2 service list -t` - list all services active

### `ros2 service type <service_name>` - see what it does when making request or receiving request

### `ros2 service find <type_name>` - find all services of a type

- like `std_srvs/srv/Empty` or `turtlesim/srv/Spawn`

### `ros2 service call <service_name> <service_type> <args>`

this will clear the window of lines:

`ros2 service call /clear std_srvs/srv/Empty`

this will spawn a new boi:

`ros2 service call /spawn turtlesim/srv/Spawn "{x: 2, y: 2, theta: 0.2, name: ''}"`

## ros2 interface

### `ros2 interface show <msg_type>` - prints like docstring

here, returns are structured like:

```bash
<request_structure>
---
<response_structure>
```

## RQT Commands

### serivce caller - where you can look at topics and call stuff manually

`rqt`

### graph - to see the graph of how nodes are communicate with eachother

`rqt_graph`
