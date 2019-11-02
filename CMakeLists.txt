cmake_minimum_required(VERSION 3.6)
project(MDPlot)

set(CMAKE_CXX_STANDARD 11)

file(GLOB SOURCES
        *.h
        *.cpp
        *.c
        )
add_executable(MDPlot main.cpp globaldata.cpp globaldata.h drawing.cpp drawing.h)
target_link_libraries(MDPlot m)

find_package(GLUT REQUIRED)
find_package(OpenGL REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11")
include_directories(GL)

set(OpenGlLinkers -lglut -lGLU -lGL) # setting all the Glut libraries as one variable.

target_link_libraries(MDPlot  ${OpenGlLinkers})

