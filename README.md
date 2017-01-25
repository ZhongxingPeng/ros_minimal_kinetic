# The origin of this ROS
This minimal version of ROS is started from bare bones **ROS-Comm**.

1. Fetch the core packages as follows

	`bash
	$ rosinstall_generator ros_comm --rosdistro kinetic --deps --wet-only --tar > kinetic-ros_comm-wet.rosinstall
	$ wstool init -j8 src kinetic-ros_comm-wet.rosinstall
	`

1. Resolve dependencies

	`bash
	$ rosdep install --from-paths src --ignore-src --rosdistro kinetic -y
	`

1. Buid catkin workspace

	`bash
	$ ./src/catkin/bin/catkin_make_isolated --install -DCMAKE_BUILD_TYPE=Release
	$ source ~/ros_catkin_ws/install_isolated/setup.bash
	`
