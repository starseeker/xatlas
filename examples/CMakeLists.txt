include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}
	${CMAKE_CURRENT_SOURCE_DIR}/..
	)

find_package(Threads)

add_executable(xatlas_ex
  	example.cpp
  	stb_image_write.c
  	tiny_obj_loader.cpp
	)
target_link_libraries(xatlas_ex xatlas Threads::Threads)

#add_executable(xatlas_c99 example_c99.c)
#add_executable(xatlas_uvmesh example_uvmesh.cpp)
