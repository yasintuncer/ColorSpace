cmake_minimum_required(VERSION 3.16)
project(ColorSpace)

set(CMAKE_CXX_STANDARD 11)
set(COLORSPACE_LIB_DIR ${CMAKE_INSTALL_PREFIX}/lib)
set(COLORSPACE_INCLUDE_DIR ${CMAKE_INSTALL_PREFIX}/include)

add_library(ColorSpace STATIC src/ColorSpace.cpp src/Conversion.cpp)

target_include_directories(ColorSpace PUBLIC src)

file(GLOB includes ${PROJECT_SOURCE_DIR}/src/*.h)

#install
install(TARGETS ColorSpace DESTINATION ${COLORSPACE_LIB_DIR})
install(FILES ${includes} DESTINATION ${COLORSPACE_INCLUDE_DIR})

