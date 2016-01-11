include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

aux_source_directory(include header)
aux_source_directory(src source)

add_executable(basecode ${source})
target_link_libraries(basecode
    ${SuiteSparse_LIBRARIES}
    ${GLUT_LIBRARIES}
    ${OPENGL_LIBRARIES}
)
