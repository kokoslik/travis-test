cmake_minimum_required(VERSION 3.0)
project(travis-test)

set(CMAKE_CXX_STANDARD 17)
add_executable(travis-test travis-test.cpp)

install(TARGETS travis-test RUNTIME DESTINATION "/opt/travis-test")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "kokoslik")
include(CPack)