cmake_minimum_required(VERSION 3.17)

project(mikktspace)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

add_library(
    ${CMAKE_PROJECT_NAME} STATIC
    mikktspace.h
    mikktspace.cpp
)

set(CMAKE_CONFIGURATION_TYPES "Debug;Release")
set_target_properties(${CMAKE_PROJECT_NAME} PROPERTIES PUBLIC_HEADER mikktspace.h)


install(TARGETS mikktspace
    LIBRARY
    CONFIGURATIONS Debug Release
    ARCHIVE DESTINATION ${${PACKAGE_NAME}_LIBS_DIR}
    PUBLIC_HEADER DESTINATION ${${PACKAGE_NAME}_INCLUDE_DIR}
)
