cmake_minimum_required(VERSION 3.1)

project(cstb)

set (CMAKE_CXX_STANDARD 11)

#general settings
file(GLOB STB_SOURCES
    cstb.cpp
)

set(STB_STATIC "no" CACHE STRING "Build as a static library")
set(STB_LIBRARIES )

#add library and link
if (STB_STATIC)
    add_library(cstb STATIC ${STB_SOURCES})
else (STB_STATIC)
    add_library(cstb SHARED ${STB_SOURCES})
endif (STB_STATIC)

target_include_directories(cstb PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(cstb PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/stb)