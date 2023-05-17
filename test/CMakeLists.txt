cmake_minimum_required(VERSION 3.14)

project(PicoDebounceButtonTests LANGUAGES CXX)

include(../cmake/project-is-top-level.cmake)
include(../cmake/folders.cmake)
include(../cmake/windows-set-path.cmake)

# ---- Dependencies ----

if(PROJECT_IS_TOP_LEVEL)
  find_package(PicoDebounceButton REQUIRED)
  enable_testing()
endif()

# ---- Tests ----

add_executable(PicoDebounceButton_test source/PicoDebounceButton_test.cpp)
target_link_libraries(PicoDebounceButton_test PRIVATE PicoDebounceButton::PicoDebounceButton)
target_compile_features(PicoDebounceButton_test PRIVATE cxx_std_20)

add_test(NAME PicoDebounceButton_test COMMAND PicoDebounceButton_test)

# ---- End-of-file commands ----

add_folders(Test)
