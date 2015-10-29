file(GLOB EXAMPLES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

foreach(file_path ${EXAMPLES})
  get_filename_component(EXE_NAME ${file_path} NAME_WE)
  add_executable(${EXE_NAME}  ${file_path})
  target_link_libraries(${EXE_NAME} framework)
endforeach()

