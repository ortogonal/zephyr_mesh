# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

option(BUILD_ZEPHYR_BACKEND "Build for Zephyr" ON)
option(BUILD_QT_BACKEND "Build Qt OSAL/HAL and simulator" OFF)
option(BUILD_TESTS "Build unit tests" OFF)

if(BUILD_ZEPHYR_BACKEND)
    find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
endif(BUILD_ZEPHYR_BACKEND)

project(device-helloworld)

target_sources(app PRIVATE src/main.c)