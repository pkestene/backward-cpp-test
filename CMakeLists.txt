cmake_minimum_required(VERSION 3.1)

project(test CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_EXTENSIONS OFF)

set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g" )

message ("CMAKE_CXX_COMPILER       = ${CMAKE_CXX_COMPILER}")       
message ("CMAKE_CXX_COMPILER_ID    = ${CMAKE_CXX_COMPILER_ID}")    
message ("CMAKE_COMPILER_IS_GNUCXX = ${CMAKE_COMPILER_IS_GNUCXX}") 

option (USE_BACKWARD_UPSTREAM "Use backward-cpp upstream version" ON)

# switch between the upstream version and mine
if (USE_BACKWARD_UPSTREAM)
  add_subdirectory(external/backward-cpp)
else()
  add_subdirectory(external/backward-cpp-pk)
endif()

add_subdirectory(test)
