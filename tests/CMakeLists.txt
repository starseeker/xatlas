include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}
	${CMAKE_CURRENT_SOURCE_DIR}/..
	)

find_package(Threads)

add_executable(tests
  	test.cpp
  	tiny_obj_loader.cpp
	)
target_link_libraries(tests xatlas Threads::Threads)

