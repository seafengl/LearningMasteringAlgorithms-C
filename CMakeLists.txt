cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(Algorithms-C)

MACRO(SUBDIRLIST result curdir)
FILE(GLOB children RELATIVE ${curdir} ${curdir}/*)
SET(dirlist "")
FOREACH(child ${children})
    IF(IS_DIRECTORY ${curdir}/${child})
        LIST(APPEND dirlist ${child})
    ENDIF()
ENDFOREACH()
SET(${result} ${dirlist})
ENDMACRO()

add_definitions("/wd4819")
add_definitions("-D_CRT_SECURE_NO_WARNINGS")

include_directories(${CMAKE_SOURCE_DIR}/dirent/include)
include_directories(${CMAKE_SOURCE_DIR}/include)
file(GLOB source_src source/*.c)
add_library(Algorithms STATIC
	${source_src}
)

add_subdirectory(Example)
