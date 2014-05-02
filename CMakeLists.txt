project(meqtrees C)
cmake_minimum_required(VERSION 2.8)

set(nodave_includes
    nodave.h
    openSocket.h
    log2.h
    openS7online.h
)

set(nodave_lib_src
    nodave.c
    openSocketw.c
)

SET (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -DBCCWIN -DDAVE_LITTLE_ENDIAN -fPIC")

add_library(nodave SHARED ${nodave_lib_src} ${nodave_includes})
TARGET_LINK_LIBRARIES(nodave ws2_32)
