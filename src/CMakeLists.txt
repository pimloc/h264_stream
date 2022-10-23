add_library(BitStream STATIC)

target_sources(BitStream
  PRIVATE
    include/bs.h
    include/h264_stream.h
    include/h264_sei.h
    h264_stream.c
    h264_sei.c
)

target_include_directories(
  BitStream PUBLIC 
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>  
    $<INSTALL_INTERFACE:include>
)
