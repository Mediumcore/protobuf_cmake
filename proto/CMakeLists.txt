INCLUDE(FindProtobuf)
FIND_PACKAGE(Protobuf REQUIRED)
include_directories(${Protobuf_INCLUDE_DIRS})
file(GLOB ProtoFiles "${CMAKE_CURRENT_SOURCE_DIR}/*.proto")
PROTOBUF_GENERATE_CPP(PROTO_SRC PROTO_HEADER  ${ProtoFiles})
ADD_LIBRARY(proto ${PROTO_HEADER} ${PROTO_SRC})
target_link_libraries(proto ${Protobuf_LIBRARIES})

