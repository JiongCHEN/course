include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

aux_source_directory(include header)
aux_source_directory(src source)

add_executable(hot2 ${source})
target_link_libraries(hot2
    ${SuiteSparse_LIBRARIES}
    ${GLUT_LIBRARIES}
    ${OPENGL_LIBRARIES}
)
