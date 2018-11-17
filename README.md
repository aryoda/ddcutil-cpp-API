# ddcutil-cpp-API
A C++ wrapper for the C-based library ddcutil to provide a clean API for C++ without exposing the C details

`ddcutil` is a Linux command line program including a C-API for managing monitor settings,
such as brightness, color levels, and input source by communicating with monitors using command that are standardized in the
**MCCS (Monitor Control Command Set)** specification.

For details see:

* ddcutil home page: http://www.ddcutil.com/
* ddcutil source code: https://github.com/rockowitz/ddcutil
* Qt-base user interface using `ddcutil`: https://github.com/rockowitz/ddcui

# Current Status

UML modelling in progress, first C++ implementation planned as next step...



# Artefacts and Tools

The UML models (class diagrams etc.) are maintained using the **Umbrello UML Modeler** (https://umbrello.kde.org/).

You can find the UML models and other concepts in the `concepts` sub folder of this repository



# Build tools

To build the source code use Qt Creator 4.5.x or higher.

I am using Ubuntu 18.04 with Qt Creator 4.5.2 and Qt 5.9.5 at the moment.

Just open the "subdirs" project (= project group) file `ddcutil_cpp_API_project_group.pro`
in the root folder of this repository.

BTW: The `ddcutil` source code will be included in the build process using a Git sub module to "pin" a stable version.



# History

This Git repository was created to implement an answer for the change request https://github.com/rockowitz/ddcutil/issues/65



# License

GPL-3
