# ddcutil C++ API (library)

A C++ wrapper library for the C-based library [ddcutil](http://www.ddcutil.com/) to provide a clean API for C++ without exposing the C details

`ddcutil` is a Linux command line program including a C-API for managing monitor settings,
such as brightness, color levels, and input source by communicating with monitors using command that are standardized in the
**MCCS (Monitor Control Command Set)** specification.

This Git repository was created to implement an answer for the change request https://github.com/rockowitz/ddcutil/issues/65

For details see:

* ddcutil home page: http://www.ddcutil.com/
* ddcutil source code: https://github.com/rockowitz/ddcutil
* Qt-base user interface using `ddcutil`: https://github.com/rockowitz/ddcui



# Goals

1. Provide a pure C++ API that encapsulates all ddcutil's C API calls (no need to know them)
1. Use exceptions to encapsulate C API status return codes and reduce if cascades
1. Care for the correct allocation/deallocation of memory and C API handles (e. g. via [smart pointers](https://en.cppreference.com/w/cpp/memory) like `unique_ptr` and `shared_ptr`)
1. Use only STL containers (and can be compiled "stand-alone" and is independent of any GUI framework like Qt)
1. Supports logging (with any logging framework)
1. The API shall be thread-safe and support async calls via multi-threading for a better user-experience
1. Support for easy unit testing of clients (e. g. mocking of physical displays)



# Current Status

Experimential!

- UML modelling in progress
- first C++ implementation planned as next step...



# Concepts & Documentation

You can find the UML models and other concepts in the `concepts` sub folder of this repository

The UML models (class diagrams etc.) are maintained using the **Umbrello UML Modeler** (https://umbrello.kde.org/).

The UML models are stored using the `XMI` file format so you can use other UML tools too.



# Build tools

To build the source code use Qt Creator 4.5.x or higher.

I am using Ubuntu 18.04 with Qt Creator 4.5.2 and Qt 5.9.5 at the moment.

Just open the "subdirs" project (= project group) file `ddcutil_cpp_API_project_group.pro`
in the root folder of this repository.

BTW: The `ddcutil` source code will be included in the build process using a Git sub module to "pin" a stable version.



# 1st-time building from the sources

Apply the following steps if you clone and build the repo for the first time:

1. Clone the repo: `git clone git@github.com:aryoda/ddcutil-cpp-API.git`
2. Install the submodules after cloning the repository:
   `git submodule update --init`
3. Build the `ddcutil` shared library (required only once so that the library can be referenced from the CPP library):

   Open a terminal in `ddcutil_submodule` sub folder and execute these commands:
   ```
   ./configure
   make
   # sudo make install   # not required!
   ```
   In case of problems (e. g. missing libraries or build tools) follow the original build instructions of `ddcutil`: http://www.ddcutil.com/building/

   Check that the `ddcutil` binaries have been built successfully: You must find the libraries (mainly `libddcutil.so`) in the sub folder `src/.libs/`
   
4. TODO: Build the Qt project...


   
# License

GPL-3

3rd-party sources may have other licenses (e. g. `ddcutil` has GPL-2).

