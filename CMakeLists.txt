cmake_minimum_required(VERSION 3.10)
project(basic-voxel-engine)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)
if("${CMAKE_SOURCE_DIR}" STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}")
    set(BVE_STANDALONE ON)
endif()
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake")
find_package(Vulkan REQUIRED)
find_package(mono REQUIRED)
option(BVE_BUILD_EXECUTABLE "Build basic-voxel-engine as an executable" ${BVE_STANDALONE})
add_subdirectory("vendor")
add_subdirectory("src")