cmake_minimum_required(VERSION 3.7)
project(INTEL-SA-00075-Linux-Detection-And-Mitigation-Tools
	LANGUAGES C 
	VERSION 0.8)

# Creates an executable for interface to library
add_executable(INTEL-SA-00075-Unprovisioning-Tool src/INTEL-SA-00075-Unprovisioning-Tool.c
                                                  src/INTEL-SA-00075.c)
add_executable(INTEL-SA-00075-Discovery-Tool src/INTEL-SA-00075-Discovery-Tool.c
                                             src/INTEL-SA-00075.c)


target_include_directories(INTEL-SA-00075-Unprovisioning-Tool
   PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/src>
)

target_include_directories(INTEL-SA-00075-Discovery-Tool 
   PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/src>
)


install(TARGETS INTEL-SA-00075-Unprovisioning-Tool DESTINATION bin)
install(TARGETS INTEL-SA-00075-Discovery-Tool DESTINATION bin)
