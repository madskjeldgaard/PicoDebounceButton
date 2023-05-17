cmake_minimum_required(VERSION 3.14)

include(cmake/prelude.cmake)

project(
  PicoDebounceButton
  VERSION 0.1.0
  DESCRIPTION "Button debouncing for the Raspberry Pi Pico SDK"
  HOMEPAGE_URL " "
  LANGUAGES NONE)

include(cmake/project-is-top-level.cmake)
include(cmake/variables.cmake)

# ---- Declare library ----

add_library(PicoDebounceButton_PicoDebounceButton INTERFACE)
add_library(PicoDebounceButton::PicoDebounceButton ALIAS
            PicoDebounceButton_PicoDebounceButton)

set_property(TARGET PicoDebounceButton_PicoDebounceButton
             PROPERTY EXPORT_NAME PicoDebounceButton)

target_include_directories(
  PicoDebounceButton_PicoDebounceButton ${warning_guard}
  INTERFACE "$<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>")

target_compile_features(PicoDebounceButton_PicoDebounceButton
                        INTERFACE cxx_std_20)

# ---- Install rules ----

if(NOT CMAKE_SKIP_INSTALL_RULES)
  include(cmake/install-rules.cmake)
endif()

# ---- Developer mode ----

if(NOT PicoDebounceButton_DEVELOPER_MODE)
  return()
elseif(NOT PROJECT_IS_TOP_LEVEL)
  message(
    AUTHOR_WARNING
      "Developer mode is intended for developers of PicoDebounceButton")
endif()

include(cmake/dev-mode.cmake)
