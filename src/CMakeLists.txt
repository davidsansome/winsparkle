cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_C_FLAGS -Wall)
list(APPEND CMAKE_CXX_FLAGS -Wall)

add_definitions(-DBUILDING_WIN_SPARKLE -DUNICODE -D_UNICODE)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../3rdparty/wxWidgets/include)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/../3rdparty/wxWidgets/include)

set(SOURCES
  appcast.cpp
  dll_api.cpp
  dllmain.cpp
  download.cpp
  error.cpp
  settings.cpp
  threads.cpp
  ui.cpp
  updatechecker.cpp
  winsparkle.rc
)

set(HEADERS
  ../include/winsparkle.h
  ../include/winsparkle-version.h
)

add_library(winsparkle SHARED
  ${SOURCES}
)

target_link_libraries(winsparkle
  wininet
  version
  wxWidgets
  expat
)

install(TARGETS winsparkle
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION bin
  ARCHIVE DESTINATION lib
)

install(FILES ${HEADERS} DESTINATION include)
