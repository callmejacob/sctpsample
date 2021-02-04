cmake_minimum_required(VERSION 3.13)
project(HelloWorld)

set(CMAKE_CXX_STANDARD 14)

find_library(SCTP_LIBRARY sctp)
find_library(PROTOBUF_LIBRARY protobuf)

add_executable(client client.cpp data.pb.cc)
target_link_libraries(client ${SCTP_LIBRARY} ${PROTOBUF_LIBRARY})

add_executable(server server.cpp main.cpp data.pb.cc)
target_link_libraries(server ${SCTP_LIBRARY} ${PROTOBUF_LIBRARY})