include_directories(${PROJECT_SOURCE_DIR}/include/semantic)
include_directories(${PROJECT_SOURCE_DIR}/include/parser)

add_library(semantic-lib chocopy_semant.cpp chocopy_type.cpp)
target_link_libraries(semantic-lib parser-lib fmt::fmt)

add_executable(semantic chocopy_semant.cpp chocopy_type.cpp)
target_link_libraries(semantic parser-lib fmt::fmt)
target_compile_definitions(semantic PUBLIC -DPA2=1)
