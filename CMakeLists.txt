cmake_minimum_required(VERSION 2.8.12)

set(CMAKE_C_COMPILER "gcc")
set(CMAKE_CXX_COMPILER "g++")

project(proEigenGWAS)

include_directories(include/)

#set(CMAKE_CXX_FLAGS "-std=c++0x -O3 -lrt")
set(CMAKE_CXX_FLAGS "-std=c++0x -O3")


IF (NOT DEFINED SSE_SUPPORT)
    SET(SSE_SUPPORT 0)
ENDIF()
ADD_DEFINITIONS(-DSSE_SUPPORT=${SSE_SUPPORT})

IF (NOT DEFINED DEBUG)
    SET(DEBUG 0)
ENDIF()
ADD_DEFINITIONS(-DDEBUG=${DEBUG})

add_executable(proEG src/propca.cpp src/genotype.cpp src/storage.cpp)
