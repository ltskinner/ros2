# Understanding Nodes

Each node in ROS should be responsible for a `single` purpose

- one for controlling wheel motors
- one for controlling a laser range finder
- etc

Nodes can send and receive data to other nodes via:

- topics
- services
- actions
- parameters
