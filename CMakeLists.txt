cmake_minimum_required(VERSION 3.21)

project(
    BIOGPS
    DESCRIPTION "OPAL"
)

add_library(
  opal
  src/opal.h
  src/opal.cpp
)

target_include_directories(
  opal
  PUBLIC
  src/
)

target_compile_options(
  opal
  PRIVATE
  $<$<BOOL:${UNIX}>:-mavx2>
  $<$<BOOL:${MSVC}>:/arch:AVX2>
)
