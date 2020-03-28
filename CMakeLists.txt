cmake_minimum_required(VERSION 3.0)
project(travis-test VERSION 0.0.$ENV{TRAVIS_BUILD_NUMBER})

set(BUILD_NUMBER $ENV{TRAVIS_BUILD_NUMBER})
configure_file(version.h.in version.h @ONLY)

set(CMAKE_CXX_STANDARD 17)
include_directories(${CMAKE_CURRENT_BINARY_DIR})
add_executable(travis-test travis-test.cpp)

install(TARGETS travis-test RUNTIME DESTINATION "/opt/travis-test")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "kokoslik")
include(CPack)