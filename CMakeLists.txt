cmake_minimum_required(VERSION 3.22)

project(
  h264
  VERSION 0.0.1
  DESCRIPTION "Library to wirte NAL to h264l"
  LANGUAGES C
)

add_subdirectory(src)

install(
  TARGETS BitStream EXPORT BitStreamTargets
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib
  RUNTIME DESTINATION bin
  INCLUDES DESTINATION include
)

#if external dependencies added then would need to generate the config cmake file
install(
  EXPORT BitStreamTargets
  FILE BitStreamConfig.cmake
  NAMESPACE H264::
  DESTINATION lib/cmake/h264
)

#g++ openRTSP.cpp playCommon.cpp -I . -I ../liveMedia/include -I ../liveMedia -I ../groupsock/include -I ../UsageEnvironment/include -I ../BasicUsageEnvironment/include ../liblive555.so -o openRTSP
#LD_LIBRARY_PATH=../ ./openRTSP
