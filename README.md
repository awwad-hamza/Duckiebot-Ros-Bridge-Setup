# Duckiebot ROS1 ↔ ROS2 Bridge Guide

This guide shows how to connect a **ROS2 Container** to a **ROS1 Duckiebot** using `ros1_bridge`.

At the end you will be able to:
- Receive Duckiebot ROS1 topics in ROS2
- Send ROS2 messages to ROS1 nodes

Architecture:
Duckiebot (ROS1 master)

│

│ 
ROS1

▼

ros1_bridge container 

│

│ ROS2

▼

Laptop ROS2 

>Important:  
**Do NOT run `roscore` manually for this setup.**  
If you run the container from within the duckiebot the ROS1 master will remain on automatically.

# Download the ROS1 Bridge Image
Pull the official ROS bridge container:
```
docker pull ros:foxy-ros1-bridge
```
Verify:
```
docker images | grep ros1-bridge
```
# Define Robot Variables