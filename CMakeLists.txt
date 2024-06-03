cmake_minimum_required(VERSION 3.7.0)
project(Frick VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

add_executable(Frick src/main.cpp)
target_include_directories(Frick PRIVATE ${CMAKE_SOURCE_DIR}/include)

set_property(TARGET Frick PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "~/Documents/Frick")

set(ZLIB_LIBRARIES zlibstatic)
set(ENABLE_BOOST_WORKAROUND ON)
set(BUILD_STATIC_LIB ON)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
