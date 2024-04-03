# moveit2_plus_drake_gsoc_2024_project
A plugin to use Drake's TOPPRA algorithm with Moveit2's motion planning interface.

### Moveit / Drake interface notes
Moveit inteface:
* "The interface to the motion planners is through a ROS action or service (offered by the move_group node)."
* "generate trajectories that are properly time-parameterized accounting for the maximum velocity and acceleration limits imposed on individual joints. These limits are read from a special joint_limits.yaml configuration file that is specified for each robot."
* Files to make https://moveit.picknik.ai/main/_images/lerp_planner.png
  * drake_toppra_planner_maanager.cpp
  * drake_toppra_planning_context.cpp
  * drake_toppra_interface.cpp
  * drake_toppra_interface_plugin_description.xml
  * package.xml
    
### TO DO:
* Figure out how to use Drake's implementation of TOPPRA
* Look at move_group node for motion planner interface via ROS action/service
* Side quest: validateworkspacebounds seems to oporate when field aren't filled in???
* Side quest: planning adapter tutorial is for ros melodic???

### Project Journal
4/2
* Read through the Moveit planning pipeling documentation.
* Browsed the lastest papers on TOPP yes there are more advanced algoritms to handle third order constraints (i.e. jerk limits) but Drake implemented TOPPRA and part of the project is interfacing with Drake, so I'll stick with that.
* Stared installing Drake

4/1
* Finished pick place tutorial -had to bump up max distance for connect stage to accept solution
* Starting to figure out Drake's implementation of TOPPRA
* Read about the Ruckig library - it looks like it should support torque limits, but I can't find any documentation the clearly states that is does. Anyways, TOPPRA will be a useful addition to Moveit if for no other reason than to give an example interface for Drake.
* Uploaded senior design code to github. Fun walk down memory lane.
* Finalized GSoC application

3/27
* Switching to TOPPRA

3/26/24
* Working through pick and place tutorial
* Read up on direct collocation
* Looked through interface files

3/25/24
* Synced repository
* Sumbitted application draft
