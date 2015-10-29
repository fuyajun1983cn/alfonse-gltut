file(GLOB EXAMPLES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

foreach(file_path ${EXAMPLES})
  get_filename_component(EXE_NAME ${file_path} NAME_WE)
  if(NOT (EXE_NAME STREQUAL "LightEnv"))
  add_executable(${EXE_NAME}  ${file_path} LightEnv.cpp)
  target_link_libraries(${EXE_NAME} framework)
  endif()
endforeach()

file(COPY data DESTINATION ${CMAKE_CURRENT_BINARY_DIR})