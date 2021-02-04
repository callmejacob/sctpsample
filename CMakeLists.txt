cmake_minimum_required(VERSION 3.13)
project(HelloWorld)

set(CMAKE_CXX_STANDARD 14)

find_library(SCTP_LIBRARY sctp)

add_executable(client client.cpp)
target_link_libraries(client ${SCTP_LIBRARY})
