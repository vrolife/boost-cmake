cmake_minimum_required(VERSION 3.12)

if(ANDROID_PLATFORM)
    set(CMAKE_TOOLCHAIN_FILE $ENV{ANDROID_NDK_HOME}/build/cmake/android.toolchain.cmake)
endif()

project(cmake-boost)

include(boost.cmake)

add_boost_libs(program_options VERSION 1.81.0)

add_executable(example example.cpp)
target_link_libraries(example PRIVATE Boost::program_options)
