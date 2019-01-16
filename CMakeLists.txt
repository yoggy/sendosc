cmake_minimum_required(VERSION 3.1)

project(sendosc)
set (CMAKE_CXX_STANDARD 11)

if(WIN32)
  include_directories( c:\\local\\oscpack_1_1_0\\include )
  
  if (CMAKE_BUILD_TYPE STREQUAL "Debug")
    link_directories( c:\\local\\oscpack_1_1_0\\lib\\Debug )
  else()
    link_directories( c:\\local\\oscpack_1_1_0\\lib\\Release )
  endif()
  set(LIBS ${LIBS} ws2_32 winmm)

elseif(APPLE)
  include_directories(/usr/local/include/oscpack)
  link_directories(/usr/local/lib)
  set(CMAKE_CXX_FLAGS "-g -Wall")
  set(CMAKE_C_FLAGS "-g -Wall")
else()
  include_directories(/usr/include/oscpack)
  include_directories(/usr/local/include/oscpack)
  link_directories(/usr/local/lib)
  set(CMAKE_CXX_FLAGS "-g -Wall")
  set(CMAKE_C_FLAGS "-g -Wall")
endif()

add_executable(sendosc sendosc.cpp)
target_link_libraries(sendosc oscpack ${LIBS})

INSTALL(TARGETS sendosc RUNTIME DESTINATION bin)

