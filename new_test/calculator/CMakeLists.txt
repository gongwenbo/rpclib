cmake_minimum_required(VERSION 3.0.0)
project(calculator)

include_directories(../../include)
#find_package(librpc REQUIRED PATHS ../../build)
link_directories(../../build)
add_executable(calculator_server calculator_server.cc)
target_link_libraries(calculator_server rpc pthread)
set_target_properties(
        calculator_server
        PROPERTIES
        CXX_STANDARD 14
        COMPILE_FLAGS "${CMAKE_CXX_FLAGS} ")
#target_compile_definitions(calculator_server PUBLIC ${RPCLIB_COMPILE_DEFINITIONS})

add_executable(calculator_client calculator_client.cc)
target_link_libraries(calculator_client rpc pthread)
set_target_properties(
        calculator_client
        PROPERTIES
        CXX_STANDARD 14
        COMPILE_FLAGS "${CMAKE_CXX_FLAGS} ")
#target_compile_definitions(calculator_client PUBLIC ${RPCLIB_COMPILE_DEFINITIONS})



