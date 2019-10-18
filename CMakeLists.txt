cmake_minimum_required(VERSION 3.0.0)
project(process_monitor)

if (UNIX)
	add_definitions(-std=c++11)
endif()

if (WIN32)
	include_directories(
		D:/apps/Python37/include
	)
else()
	include_directories(
                /usr/include/python2.7
        )
endif()

include_directories(
	deps/matplotlibpp
	src
)

if (WIN32)
link_directories(
	D:/apps/Python37/libs
)
else()
link_directories(
	#/usr/lib/python2.7/site-packages
)
endif()


set(SRC
    src/main.cpp
)

add_executable(process_monitor ${SRC})