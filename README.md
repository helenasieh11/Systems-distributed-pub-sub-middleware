# Systems-distributed-pub-sub-middleware

# ROB 320 (Winter 2026): Robot Operating System:
Below are some of the projects that I worked on in this class. These projects range from driving in a star to wall following to developing a breadth first search path planning algorithm.

**Project 1: Teleop Keyboard**
- [Teleop Robot Demo](https://drive.google.com/file/d/1JDO_9i6iPOjwlvE_qn_iKzP-hK8aV8kA/view?usp=sharing)
- [Teleop Terminal Demo](https://drive.google.com/file/d/1JDO_9i6iPOjwlvE_qn_iKzP-hK8aV8kA/view?usp=sharing)

The objective of the first project is to implement a command line interface (CLI) for keyboard teleoperation of the MBot Omni. Once complete, a user should be able to drive the MBot using the WASD keys to move forward, left, right, and backwards, the QE keys to rotate counter-clockwise and clockwise, and the spacebar to stop.

This project requires you to implement two programs: mbot_driver and teleop_keyboard. The mbot_driver program will read drive commands from stdin and forward them to the MBot Control Board via USB. This program is designed to interface with the other two programs using unnamed pipes from the command line. The teleop_keyboard program will open a named pipe (FIFO) for parsing keyboard input. It will read individual characters from the FIFO and convert them into drive commands. To write characters to the FIFO, use executables such as echo or tee.

**Project 2: Click to Drive**
- [Drive Robot Demo](https://drive.google.com/file/d/1oqbRiV8SvDKO9LbilTiHVXMh3R_q4KB3/view?usp=sharing)
- [Drive Terminal Demo](https://drive.google.com/file/d/1JDO_9i6iPOjwlvE_qn_iKzP-hK8aV8kA/view?usp=sharing)

The objective of the second project is to implement driver programs to enable a click to drive graphical user interface (GUI) running on your local machine to stream laser range and odometry data from and send position commands to the MBot. This will be accomplished by using sockets to communicate over a wireless network using TCP.

This project requires you to implement two programs: mbot_driver and lidar_driver. The mbot_driver in project 2 is very similar to project 1 in that it will interface via USB with the MBot Control Board. However, rather than receiving velocity commands via a pipe, it will host a server that will receive position commands from and send odometry data to a client that connects to it. The lidar_driver will interface with the RPLIDAR A1 and will host a server that will send laser range data to a client that connects to it. Pictured below is the click to drive GUI running successfully. Here is a link to a video demonstration of the GUI.

**Project 3: Robot Interprocess eXchange**
The objective of the third project is to develop a full publish/subscribe system to enable asynchronous streaming of messages between nodes via topics. You will implement the core functionality of the Robot Interprocess eXchange (RIX), which consists of 4 classes: Node, Publisher, Subscriber, and Mediator.

**Project 4: Forward Kinematics**

<img width="586" height="296" alt="Screenshot 2026-08-18 at 3 06 48 PM" src="https://github.com/user-attachments/assets/396e15e9-d40b-45a3-96bb-de7486a6bbd7" />

The objective of the fourth project is to develop a library that enables the efficient distribution of and transformation between coordinate frames. You will use a textual description of a robot (JRDF, which has all of the rules of URDF but is formatted as JSON rather than XML), to determine the geometric relationships between the links and joints that comprise a robot. A link is a rigid body with inertia, visual features, and collision properties. A joint represents the kinematic relationship between two links, often a rotation (revolute or continuous joint) or a translation (prismatic joint). In this project, the geometric relationships among links and joints are represented as 3D homogenous transformations. You will use the Eigen Geometry library for all linear algebra operations in this project.

**Project 5: Inverse Kinematics**

<img width="833" height="455" alt="Screenshot 2026-08-18 at 3 04 52 PM" src="https://github.com/user-attachments/assets/c1548acb-c8be-4a72-bb54-dabc5d4053e7" />

The objective of the fifth project is to implement inverse kinematics using Gauss-Newton method. To do this, you must compute the geometric Jacobian for a serial chain robot and use the Moore-Penrose pseudoinverse of the Jacobian for iterative optimization. There is only a single interface that you are responsible for implementing in this project: KinematicsSolver. 

The KinematicsSolver class provides methods to solve forward kinematics and inverse kinematics problems using numerical methods. You will implement four key methods in kinematics_solver.cpp:

solve_fk - Forward kinematics
get_jacobian - Jacobian matrix computation
iterate_ik - Single iteration of inverse kinematics using Gauss-Newton
solve_ik (two overloads) - Complete inverse kinematics solver





