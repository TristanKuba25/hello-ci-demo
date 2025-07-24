cmake_minimum_required(VERSION 3.25)
project(hello LANGUAGES CXX)

add_executable(hello hello.cpp)
set_target_properties(hello PROPERTIES CXX_STANDARD 17)

install(TARGETS hello DESTINATION bin)

include(GNUInstallDirs)

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Tristan SOL")
set(CPACK_DEBIAN_PACKAGE_ARCHITECTURE "arm64")
set(CPACK_PACKAGE_VERSION "0.1.0")
set(CPACK_PACKAGE_FILE_NAME "hello_${CPACK_PACKAGE_VERSION}_arm64")
include(CPack)
