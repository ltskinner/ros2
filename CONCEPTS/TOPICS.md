# Topics

Nodes have a publisher, which sends a **message** to the `topic`

Then, other nodes have subscribers that listen to the `topic` and receive the **message**

Relationship types:

- one to many
- many to one
- many to many

## What makes up a topic (some - helpful for framing)

e.g. `geometry_msgs/msg/Twist`

the source package:

- rcl_interfaces
- geometry_msgs
- <package_udefs>

which have types, like:

- ParameterEvent
- Log
- Twist
- Color
- Pose

remember these bro?

Not sure the proper term for the middle /msg/ part tho
