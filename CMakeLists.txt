# This is the root ITK CMakeLists file.
cmake_minimum_required(VERSION 3.0)
if(COMMAND CMAKE_POLICY)
  cmake_policy(SET CMP0003 NEW)
endif()

project(semfilter)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})

find_package(SlicerExecutionModel REQUIRED)
include(${SlicerExecutionModel_USE_FILE})

set(semfilter main.cxx SmoothingFilter.hxx SmoothingFilter.h)

SEMMacroBuildCLI(
    NAME semfilter
    EXECUTABLE_ONLY
    TARGET_LIBRARIES ${ITK_LIBRAIRIES}
    )
