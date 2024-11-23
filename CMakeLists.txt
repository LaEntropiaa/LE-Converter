cmake_minimum_required(VERSION 3.16)

project(LE-Converter LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(LE-Converter main.cpp)

include(GNUInstallDirs)
install(TARGETS LE-Converter
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
