cmake_minimum_required(VERSION 3.16)

project(LE-Converter LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(wxWidgets REQUIRED COMPONENTS net core base)
if(wxWidgets_USE_FILE) # not defined in CONFIG mode
    include(${wxWidgets_USE_FILE})
endif()

add_executable(LE-Converter main.cpp)
target_link_libraries(LE-Converter ${wxWidgets_LIBRARIES})

include(GNUInstallDirs)
install(TARGETS LE-Converter
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
