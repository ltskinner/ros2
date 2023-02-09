# ROS2 Concepts

ROS2 is a `middleware` based on an anonymous **publish/subscribe** mechanism that allows for **message passing** between different ROS processes

- `ROS Graph` - network of nodes and the connections between them by which they communicate
  - `nodes` - an entity that uses ROS to communicate with other node
  - `messages` - ROS data type used when **subscribing** or **publishing** to a **topic**
  - `topic` - nodes can publish messages to a topic, and can subscribe to receive messages from a topic
  - `discovery` - how nodes determine how to talk to each other (automatic)

## To Be Defined

- `subscribing`
- `publishing`
- `Services`
- `Actions`

## [Nodes](./NODES.md)

More on nodes - they are/can:

- Participate in the ROS graph
- Publish to a topic
- Subscribe to a topic
- Provide Services
- Provide Actions
- Use Services
- Use Actions
- Have configurable Parameters
- Nodes can be located in:
  - Same process
  - Different processes
  - Different machines

## [Topics](./TOPICS.md)

## Discovery

- 1. Upon the start of a node, it advertizes/broadcasts its presence to other nodes on the same `ROS domain`. Nodes respond to heard advertizements with their own information
  - Note, use the `ROS_DOMAIN_ID` env var
- 2. Nodes will re-advertize so that connections can be made with new entities joining the network (after the initial window)
- 3. Nodes also advertise when they go offline

## Services

Ok this is sweet - you get to this from `rqt`

And you can like manually specify parameters for things and execute the routine that service performs (e.g. spawning a new turtle)

- when you do this you have to hit the `call` button to actually execute it
- also, for each object copy that exists in the graph or whatever, youll see all their /paths/ appear in the service list
