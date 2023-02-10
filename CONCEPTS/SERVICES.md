# Serivces

Sercives are another method of communication

- follow the `call-and-response` model
  - (as oopposed to the `publisher-subscriber` model - topics)
- services only provide data when they are **explicitly** called by a client
  - (as opposed to data streams that get continual updates - topics)
- there can only be one `server` for a service, but can be any number of `clients`

## ros2 service list

so here, youll see that there are 6 standard services for each node:

- /<node>/describe_parameters
- /<node>/get_parameter_types
- /<node>/get_parameters
- /<node>/list_parameters
- /<node>/set_parameters
- /<node>/set_parameters_atomically
