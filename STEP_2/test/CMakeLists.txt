include_directories(../src)

file(GLOB cxx_files *.cpp)
foreach(filename ${cxx_files})
  get_filename_component(target ${filename} NAME_WE)
  add_executable(${target} ${filename})
  target_link_libraries(${target} ${PROJECT_NAME})
  add_test(NAME ${target}
           COMMAND ${target})
endforeach(filename)