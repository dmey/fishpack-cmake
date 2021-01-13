# FISHPACK-CMake (https://github.com/dmey/fishpack-cmake).
# Copyright (C) 2019 D. Meyer.

cmake_minimum_required(VERSION 3.0)
project(FISHPACK Fortran)

include(CTest)

option(USE_REAL8 "Use real8 instead of real4" ON)

if (NOT CMAKE_BUILD_TYPE)
    message(STATUS "No build type selected, default to Release")
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Build type (default Release)" FORCE)
endif()

if(CMAKE_Fortran_COMPILER_ID MATCHES "GNU")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -cpp -fallow-argument-mismatch")
    set(CMAKE_Fortran_FLAGS_DEBUG "${CMAKE_Fortran_FLAGS} ${CMAKE_Fortran_FLAGS_DEBUG} -fbacktrace -Wextra -ffpe-trap=invalid,zero,overflow,underflow")
    if (USE_REAL8)
        set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -fdefault-real-8 -fdefault-double-8")
    endif()
elseif(CMAKE_Fortran_COMPILER_ID MATCHES "Intel")
    set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -fpp")
    set(CMAKE_Fortran_FLAGS_DEBUG "${CMAKE_Fortran_FLAGS} -traceback -fpe-all0")
    if (USE_REAL8)
        set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -r8")
    endif()
else()
    message(FATAL_ERROR "Only gfortran and ifort compilers are supported")
endif()

add_subdirectory(src)
if(TESTS)
    add_subdirectory(test)
endif()