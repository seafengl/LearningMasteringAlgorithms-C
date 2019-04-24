
SUBDIRLIST(SAMPLE_SUBDIRS ${CMAKE_CURRENT_LIST_DIR})
foreach(SAMPLE_SUBDIR ${SAMPLE_SUBDIRS})
    message(STATUS "add sample ${SAMPLE_SUBDIR}")
    file(GLOB sample_src ${CMAKE_CURRENT_LIST_DIR}/${SAMPLE_SUBDIR}/*.cpp
                        ${CMAKE_CURRENT_LIST_DIR}/${SAMPLE_SUBDIR}/*.c)
    add_executable(${SAMPLE_SUBDIR} ${sample_src})
	target_link_libraries(${SAMPLE_SUBDIR} Algorithms)
endforeach()