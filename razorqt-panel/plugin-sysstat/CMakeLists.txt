cmake_minimum_required(VERSION 2.6)

set(PLUGIN "panelsysstat")


set(HEADERS
    razorsysstat.h
    razorsysstatconfiguration.h
    razorsysstatcolours.h
    razorsysstatutils.h
)

set(SOURCES
    razorsysstat.cpp
    razorsysstatconfiguration.cpp
    razorsysstatcolours.cpp
    razorsysstatutils.cpp
)

set(MOCS
    razorsysstat.h
    razorsysstatconfiguration.h
    razorsysstatcolours.h
)

set(UIS
    razorsysstatconfiguration.ui
    razorsysstatcolours.ui
)


LINK_LIBRARIES(${PLUGIN} ${SYSSTAT_LIB})

#*******************************************
include ("../BuildPlugin.cmake")
BUILD_RAZOR_PLUGIN(${PLUGIN})
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(panelsysstat_LIBRARIES
    sysstat
)
target_link_libraries(${PLUGIN}  ${panelsysstat_LIBRARIES})
