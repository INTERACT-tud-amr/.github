## Welcome to github organization of the dinovas, maintained by the project INTERACT 🙌

We, the members of the project INTERACT (intuitive Interaction for Robots among Humans), have created this github organization for all code related to the dinova's.
Code that belongs to published papers can be found on the [tud-amr github]([https://github.com/INTERACT-tud-amr]).
This organization is meant for clustering all relevant code required to show designed algorithms and demo's on the real dingo+kinova robots. 

This organization is maintained by Saray, Andreu and Clarence. 
If there are any issues, comments or questions, let us know via an issue!

Check out the [website of AMR](https://autonomousrobots.nl/) and [github page](https://github.com/tud-amr) as well!

### I want to run my own algorithm on the dinovas, which repos do I need?:
1. **[dinova](https://github.com/INTERACT-tud-amr/dinova)**: This repository contains all bring-up files to launch ROS-nodes on the dinova (dingo + kinova), kinova or dingo. This repository is already installed on the robot and can be run from there. This repository also contains a gazebo simulator for your own online simulations.
2. **[dinova_utils](https://github.com/INTERACT-tud-amr/dinova_utils)**: Some additional utils for running the dinovas in the lab are included in here.
   Currently this contains:
   - ROS-based code for merging different obstacles in the Vicon bridge to one ros-topic (required for *dinova_motion* and *dinova_grasp*).
4. **[dinova_motion](https://github.com/INTERACT-tud-amr/dinova_motion)**: This contains ROS-wrappers for local motion planners for the dinovas.
   Currently, this contains a ROS-wrapper for :
   - The geometric & reactive local motion planner *[fabrics](https://github.com/tud-amr/fabrics)*: Including goal reaching, limit avoidance and obstacle avoidance. 
5. **[dinova_grasp](https://github.com/INTERACT-tud-amr/dinova_grasp)**: This repository is required if you want to create a set of waypoints to guide the local motion planner and optimize the grasp (or place) pose in the presence of obstacles. This repository contains a ROS-wrapper for the python package: *[grasp_fabrics](https://github.com/TomasMerva/grasp_fabrics)*. This repository is *not* required if you just want to send the robot to a goal. 
6. **[dinova_task](https://github.com/INTERACT-tud-amr/dinova_grasp)**: This repository provides a relatively simple task planner using PDDL. Provide what the final scenario should be (e.g. cup1 on table1) and the PDDL-planner generates a high-level plan how to obtain this and sends requests to *dinova_motion* and *dinova_grasp* to execute this plan. This repository is *not* required if you just want to send the robot to a goal. 
7. **[visualization_utils](https://github.com/INTERACT-tud-amr/visualization_utils)**: For visualizing obstacles, the robots and humans in rviz, check out this repository.
8. **[simple_zed2_wrapper](https://github.com/INTERACT-tud-amr/simple_zed2_wrapper)**: For using the zed2 camera with human-pose recognition. 

### How to organize my workflow?
Repositories 1-5 as mentioned above are already installed on the robot under the user *dinova*. All repositories on the robot under the user *dinova* should **NOT** be changed, as it might cause issues for others. 
If you need your own version of these repositories, please install them on your own user on the robot. You can create your own user on the robot (together with one of the INTERACT members) via:
```bash
sudo adduser <first_letter+last_name>    # for example: sudo adduser jjohnsen
```
Be aware that your own user does not have sudo-rights to install new dependencies on the robot. 
Therefore it is best to also create a catkin-workspace on your own laptop ([instructions](http://wiki.ros.org/catkin/Tutorials/create_a_workspace)) and connect to the robot via:
```bash
export ROS_MASTER_URI=http://<robot_ipaddress>:11311
export ROS_IP=<laptop_ipaddress>
```
If you need a docker to run ROS1, check out *[dingo-ros-container](https://github.com/INTERACT-tud-amr/dingo-ros-container)*.

For an example of automatically running multiple ROS-commands in different terminals via ssh and on your laptop, check out the [erc-demo](https://github.com/INTERACT-tud-amr/erc_demo) on using *tmuxp-files*.

### I would like to run a complete demo!
Amazing! Check out [erc-demo](https://github.com/INTERACT-tud-amr/erc_demo) to run the demo as shown during the lab-tour at RSS 2024. 

<table>
 <tr>
  <td> One of our robots </td>
  <td> An example environment </td>
 </tr>
 <tr>
  <td> <img src="/profile/dinova.jpg" width="250"/> </td>  
  <td> <img src="/profile/robot_bar.png" width="250"/> </td>
 </tr>
</table>
