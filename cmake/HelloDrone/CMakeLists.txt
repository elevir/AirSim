cmake_minimum_required(VERSION 3.11)
project(HelloDrone)

AddExecutableSource()

target_include_directories(${PROJECT_NAME} PRIVATE
  $<BUILD_INTERFACE:${AIRSIM_ROOT}/HelloDrone>
)
target_link_libraries(${PROJECT_NAME} PRIVATE AirLib)

install(TARGETS ${PROJECT_NAME}
	EXPORT ${SOLUTION_NAME}-export
	LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
	RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)