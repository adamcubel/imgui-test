cmake_minimum_required(VERSION 3.11)

project(imgui-test LANGUAGES C CXX)

set(CMAKE_COLOR_MAKEFILE ON)

#------------------------------------------------------------------------------#
# Set the project version
#------------------------------------------------------------------------------#
set (FRAN_VERSION_MAJOR "1" CACHE STRING "Major version number")
set (FRAN_VERSION_MINOR "0" CACHE STRING "Minor version number")
set (FRAN_VERSION_PATCH "0" CACHE STRING "Patch version number")
set (FRAN_VERSION_BUILD "0" CACHE STRING "Build version number")
set (FRAN_VERSION "${FRAN_VERSION_MAJOR}.${FRAN_VERSION_MINOR}.${FRAN_VERSION_PATCH}-${FRAN_VERSION_BUILD}")

#------------------------------------------------------------------------------#

#------------------------------------------------------------------------------#
# Set the C++ Flags and definitions
#------------------------------------------------------------------------------#
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wcast-align")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wcast-qual")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wcatch-value")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wconversion")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wdisabled-optimization")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wextra")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wfloat-equal")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wformat-nonliteral")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wformat-security")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wformat-y2k")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wformat=2")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wimport")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wint-in-bool-context")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Winit-self")
if(CMAKE_BUILD_TYPE STREQUAL "Debug") #due to optimization in release need to only do during debug 
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Winline")
endif()
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Winvalid-pch")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wmissing-field-initializers")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wmissing-format-attribute")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wmissing-noreturn")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wnon-virtual-dtor")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wold-style-cast")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Woverloaded-virtual")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wpacked")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wpointer-arith")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wredundant-decls")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wredundant-tags")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wshadow")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wstack-protector")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wstrict-aliasing=2")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wsuggest-override")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wswitch-default")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wswitch-enum")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wunreachable-code")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wunused")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wunused-parameter")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wuseless-cast")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wvariadic-macros")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wwrite-strings")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wzero-as-null-pointer-constant")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pedantic")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pedantic-errors")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Weffc++") #enables warning from Effective C++

add_definitions("-enable-threadsafe")
add_definitions("-fPIC")
#------------------------------------------------------------------------------#

add_subdirectory(imgui-test)
