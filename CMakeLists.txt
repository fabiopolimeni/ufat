#
# project: ufat
#
cmake_minimum_required(VERSION 3.15)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON) #...is required...

project(ufat)

set(UFAT_LIB_SOURCES 
  ufat.c
  ufat_dir.c
  ufat_file.c
  ufat_ent.c
  ufat_mkfs.c
)

add_library(ufat STATIC ${UFAT_LIB_SOURCES})

add_executable(ufat_main main.c ya_getopt.c strcasecmp.c)
target_link_libraries(ufat_main PUBLIC ufat)
set_target_properties(ufat_main PROPERTIES OUTPUT_NAME ufat)
