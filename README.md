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

  Drake TOPPRA interface:
  * Toppra - sets up IK problem
    * Trajectory
    * Multibody plant
    * Gridpoints
    * Member functions
      * SolvePathParameterization () - solves IK problem
      * AddJointVelocityLimit - Set global velocity limits
        * Min velocity vector
        * Max velocity vector
      * AddJointAccelerationLimit - set global acceleration limits
        * Min acceleration
        * Max acceleration
        * Choose descretization type - collocation vs interpolation
      * AddJointTorqueLimit - Set global torque limits
        * Min torque vector
        * Max torque vector
      * AddFrameVelocityLimit - sets velcoity limits for a frame
        * Frame
        * Min velocity
        * Max velocity
      * AddFrameTranslationalSpeedLimit - sets frame translational velocity limt either as measured wrt to world frame or as bounded by a given trajectory
        * Frame
        * Upper limit / bounding trajectory
      * AddFrameAccelerationLimit - sets frame acceleration limt either as measured wrt to world frame or as bounded by a given trajectory
        * Frame
        * Upper limit / bounding trajectory
     
    
### TO DO:
* Figure out how to use Drake's implementation of TOPPRA
  * Learn about what a multibodyplant is in Drake
  * Create multibodyplant "adapter" for moveit
  * Create trajectory "adapter" for moveit
  * Create Eigan::VectorXD "adapter" for moveit
  * Create Frame "adapter" for moveit
* Look at move_group node for motion planner interface via ROS action/service
* Side quest: validateworkspacebounds seems to oporate when field aren't filled in???
* Side quest: planning adapter tutorial is for ros melodic???


### Project Journal
6/11
* Finally finished Manipulation exercises through ch6 which cover trajectory planning
* Started refreshing myself on Moveit's architecture.
  
4/10
* Completed ch2, ex 1.
* Submitted pull request to fix RenderDiagram error!
* Completed ch2 ex 2.
* Started ex 3.

4/9
* Started working on the manipulator course. It is much more relevant to this project compared to the underactuated robotics class.
* Started Ch2, ex1.

4/8
* Took notes on Drake's TOPPRA inputs
* Read about multibodyplant, trajectory, and frame classes
* Completed MIT UA 2.5, started 2.6

4/5
* Working on Drake tutorials (completed exercise 1.5 of MIT UA course, starting 2.5)

4/3
* Working on Drake tutorials (exercise 1.5 of MIT UA course)

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
* Submitted application draft
