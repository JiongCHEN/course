project(dgpdec)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_C_FLAGS "-Wall -Werror -ansi -pedantic")
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake/;${CMAKE_MODULE_PATH}")

find_package(SuiteSparse REQUIRED)
if(SuiteSparse_FOUND)
    include_directories(${SuiteSparse_INCLUDE_DIRS})
endif(SuiteSparse_FOUND)

find_package(OpenGL REQUIRED)

find_package(GLUT REQUIRED)
if(GLUT_FOUND)
    add_definitions(-DGL_GLEXT_PROTOTYPES)
    include_directories(${GLUT_LIBRARIES})
endif(GLUT_FOUND)

add_subdirectory(BaseCode)
add_subdirectory(Connection)
add_subdirectory(Elasticity)
add_subdirectory(Fairing)
add_subdirectory(Flatten)
add_subdirectory(Geodesics)
add_subdirectory(Hot2)
