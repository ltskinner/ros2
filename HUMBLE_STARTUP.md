# Humble

[https://docs.ros.org/en/humble/Releases.html](https://docs.ros.org/en/humble/Releases.html)

## Boilerplate setup

### [WSL 2 install](https://learn.microsoft.com/en-us/windows/wsl/install#install-wsl-command)

```powershell
# From Powershell as ADMIN

## actually do the install
wsl --install

## verify correct version
wsl -l -v
```

### [Docker Install](https://docs.docker.com/desktop/windows/wsl/)

Pretty easy, just make sure to reboot a time or two esp if there are network errors on initial pull

## First run of `humble`

```bash

docker pull osrf/ros:humble-desktop

docker run -it osrf/ros:humble-desktop
```

Above opens an interactive terminal on the run container. Inside:

```bash
ros2 pkg list

ros2 pkg executables
```

### Two Nodes One Container 0_0

```bash
ros2 run demo_nodes_py listener &
ros2 run demo_nodes_py talker
```

### Two Nodes Two Containers

Execute these in a regular terminal, these are `docker` commands - **NOT** `ros2` commands

```bash
# Terminal A
docker run -it --rm osrf/ros:humble-desktop ros2 run demo_nodes_py talker

# Terminal B
docker run -it --rm osrf/ros:humble-desktop ros2 run demo_nodes_py listener
```
