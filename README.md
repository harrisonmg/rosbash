ROSBash
===================
ROSBash provides a set of aliases and bash functions to make it more user friendly when used from the command-line.

## Installation

Simply source the *rosbash.bash* script in your *~/.bashrc*:

```bash
# Add an empty line, add the source command
echo >> ~/.bashrc && echo source `pwd`/rosbash.bash >> ~/.bashrc
source ~/.bashrc
```
    
Restart your shell for the changes to take effect.

## Usage
### Loading ROS environments
Specific ROS environments can be loaded directly in a subshell with a dedicated prompt. This is handy when you need to often switch your environment:

```bash
groovy
indigo
hydro
kinetic
```

The following commands start a new shell with a workspace environment (either devel or install) for instance:

```bash
cd ~/ros_ws
devel
```

or

```bash
cd ~/ros_ws
install
```
    
Any of these shells can be exited with the command *exit* or by pressing *Ctrl-D*.

### Manipulating ROS environment variables
The following commands gives you the list of all ROS relevant environment variables, or just those related to the network:

```bash
ros
rosnetwork
```
The next commands allow you to manipulate the environment variables:

```bash
rosmaster gita.local     # Set ROS_MASTER_URI to http://gita.local:11311
roshostname titan.local     # Set ROS_HOSTNAME to titan.local and remove ROS_IP
rosip 192.168.0.1     # Set ROS_IP to 192.168.0.1 and remove ROS_HOSTNAME
```
    
### Other useful commands

```bash
cm     # Finds the root folder of your workspace, run catkin_make and comes back to current folder
rosrefresh    # Rebuilds the index of packages in your workspace (useful if your packages are not seen)
urdf_show gita.urdf     # Display the URDF model in the GUI
xacro_show gita.xacro     # Generates the URDF from XACRO and display it in GUI
rn # rosnode list
rni # rosnode info
rte # rostopic echo
rtl # rostopic list
rti # rostopic info
```
