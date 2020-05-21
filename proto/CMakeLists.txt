INCLUDE(FindProtobuf)
FIND_PACKAGE(Protobuf REQUIRED)
include_directories(${Protobuf_INCLUDE_DIRS})

PROTOBUF_GENERATE_CPP(PROTO_SRC PROTO_HEADER message.proto)
ADD_LIBRARY(proto ${PROTO_HEADER} ${PROTO_SRC})
target_link_libraries(proto ${Protobuf_LIBRARIES})

