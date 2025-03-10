# infoware [![License](https://img.shields.io/badge/license-CC0-green.svg?style=flat)](LICENSE) [![TravisCI build status](https://travis-ci.org/ThePhD/infoware.svg?branch=master)](https://travis-ci.org/ThePhD/infoware) [![AppVeyorCI build status](https://ci.appveyor.com/api/projects/status/github/ThePhD/infoware?branch=master&svg=true)](https://ci.appveyor.com/project/ThePhD/infoware/branch/master)
C++ Library for pulling system and hardware information, without hitting the command line.


## Requirements
No non-built-in ones by default.<br />
Some libraries are required for extended functionality. See the [Configurability](#configurability) section below for details.

On Windows one needs to link to `gdi32`, `version`, `Ole32`, `OleAut32` and `wbemuuid`.

## Configurability
|CMake definition and C++ preprocessor macro|              Meaning              |Linker library|Priority|
|-------------------------------------------|-----------------------------------|--------------|--------|
|             `INFOWARE_USE_X11`            |   Use X11 for display detection   |     `X11`    | <Win32 |
|             `INFOWARE_USE_D3D`            |      Use D3D for GPU detection    |    `dxgi`    | >OpenCL|
|            `INFOWARE_USE_OPENCL`          |    Use OpenCL for GPU detection   |   `OpenCL`   |  <D3D  |
|            `INFOWARE_USE_OPENGL`          |    Use OpenGL for GPU detection   |OS-dependent\*| <OpenGL|


\*Consult the section under the `if(INFOWARE_USE_OPENGL)` condition in `CMakeLists.txt` for variants.
