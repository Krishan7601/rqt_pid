cmake_minimum_required(VERSION 2.8.3)
project(rqt_pid)
find_package(catkin REQUIRED)
catkin_package()
catkin_python_setup()

find_package(catkin REQUIRED COMPONENTS
	rospy
	rqt_gui
	rqt_gui_py
)

find_package(Boost REQUIRED COMPONENTS system)


catkin_package(
#	INCLUDE_DIRS include
#  LIBRARIES rqt_drone
	CATKIN_DEPENDS rospy rqt_gui rqt_gui_py
#  DEPENDS system_lib
)

include_directories(
	${catkin_INCLUDE_DIRS}
)

install(PROGRAMS
	scripts/rqt_pid
	DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
 )
 
install(FILES plugin.xml
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION} 
)
## Mark other files for installation (e.g. launch and bag files, etc.)
# install(FILES
#   # myfile1
#   # myfile2
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
# )
