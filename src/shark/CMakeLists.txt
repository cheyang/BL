cmake_minimum_required(VERSION 2.8)
PROJECT(SHARK)

ADD_DEFINITIONS(-g -W -Wall -D_FILE_OFFSET_BITS=64 -std=c++11 -D__STDC_FORMAT_MACROS -Wformat -Wno-deprecated -DTHREADED ${CMAKE_CXX_FLAGS})

AUX_SOURCE_DIRECTORY(./   SRC_LIST)
AUX_SOURCE_DIRECTORY(./log   SRC_LIST)
#AUX_SOURCE_DIRECTORY(./http  SRC_LIST)

INCLUDE_DIRECTORIES(
./
./log/
#./http/
/usr/local/include
)

SET(EXECUTABLE_OUTPUT_PATH ./)

LINK_DIRECTORIES(
/usr/lib/
/usr/local/lib/
)

ADD_EXECUTABLE(shark ${SRC_LIST})

#TARGET_LINK_LIBRARIES(shark pthread event evhtp)
TARGET_LINK_LIBRARIES(shark pthread)
