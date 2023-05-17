# PicoDebounceButton

This is a small library for debouncing button presses on the Raspberry Pi Pico, using the [Pico C++ SDK](https://github.com/raspberrypi/pico-sdk). It is inspired by [Bounce2](https://github.com/thomasfredericks/Bounce2).

## Example

For an example on how to use this project, see [this](https://github.com/madskjeldgaard/SimplePicoMidiController).

## Adding this library to your project

### Using CPM
The easiest way to use this in your project is to install [it using CPM](https://github.com/cpm-cmake/CPM.cmake). Add the following lines to your CMakeLists.txt. This will automatically download and include it in your CMake setup.

```cmake
# Add Debounce
CPMAddPackage("gh:madskjeldgaard/PicoDebounceButton#main")
target_link_libraries(SimplePicoMidiController PicoDebounceButton::PicoDebounceButton)
```

### Manually
If you have a project called `SimplePicoMidiController`, you can link this library in your CMakeLists.txt like so (assuming you downloaded the library and placed it in the path noted below):  

```cmake
# Add Debounce
set(PICO_DEBOUNCE_PATH "include/PicoDebounceButton")
add_subdirectory(${PICO_DEBOUNCE_PATH})
target_link_libraries(SimplePicoMidiController PicoDebounceButton::PicoDebounceButton)
```

# Contributing

See the [CONTRIBUTING](CONTRIBUTING.md) document.
