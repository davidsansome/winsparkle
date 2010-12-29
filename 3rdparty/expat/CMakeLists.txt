cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_C_FLAGS -Wall)
list(APPEND CMAKE_CXX_FLAGS -Wall)

add_definitions(-DUNICODE -D_UNICODE -DCOMPILED_FROM_DSP)

set(SOURCES
  lib/xmlparse.c
  lib/xmlrole.c
  lib/xmltok.c
  lib/xmltok_impl.c
  lib/xmltok_ns.c
)

add_library(expat STATIC
  ${SOURCES}
)
