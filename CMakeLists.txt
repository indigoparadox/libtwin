cmake_minimum_required(VERSION 3.10)

project(libtwin)

set(LIBTWIN_C_FILES src/htmlrend.c src/htmtree.c src/ui/graphicu.c)

include_directories(../libvcol/src)
include_directories(../camgraph/src)
include_directories(../camin/src)

add_library(libtwin ${LIBTWIN_C_FILES})

