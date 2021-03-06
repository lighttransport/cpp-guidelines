# cpp-guidelines

Light Transport Entertainment's C/C++ coding guidelines.

## Language version

C++11 as a basis.

It would be better codes can be compiled with C++03 compiler(to support rather old compiler and emerging platform which does not support C++11 feature yet: e.g. RISC-V based embedded processor)

Example project is available as NanoRT ( https://github.com/lighttransport/nanort )

## Platforms and compilers

Code shuld be portable and cross-platform as much as possible.

### Platform

Unixish system as a first citizen. Windows and Android/iOS second.

* Linux 64bit(Ubuntu 16.04 or later)
* macOS sierra or later
* Windows 10 or later
* Android
* iOS
* x86
* ARM
* RISC-V
* JIT system(e.g. clang/LLVM JIT)

### Compilers

* gcc
* clang
* MinGW, MSC(Visual Studio 2015 or later)

## Complier flags

* clang : Use `-Weverything -Werror -Wno-padded` as a basis and suppress all warning as much as possible
* MSC : Use `/W4`

### Memory management

Use RAII approach as much as possible: http://en.cppreference.com/w/cpp/language/raii

* Use ASAN(Addres Sanitizer) to find memory related issue.
  * No memory leaks is the best.
  * cmake package: https://github.com/arsenm/sanitizers-cmake

## Coding style

Use Google coding style as default.

https://google.github.io/styleguide/cppguide.html

Use `clang-format` to format codes.

Simple, easy-to-hack, easy-to-embed as much as possible(e.g. do not create compilex class hiearches)

## Build tools

* cmake
* premake5 
* Makefile
* ninja

## Dependency

* **NO BOOST** (except for `nanogi` project)
* Less external project dependency as much as possible(C++ STL only or NanoSTL only  preferred)
* Using header-only single C++ library preferred.

## API, SDK, Specification and Format

Use cross-platform, de-fact or standalised API/SDK/Specification/Format as much as possible.

* OpenGL, WebGL
* JSON RPC(version 2.0)
* glTF(3D data exchange)
* OpenEXR(For HDR image)
* OpenCL

### Recommended third party libraries

* NanoRT(raytracing kernel) https://github.com/syoyo/tinydngloader
* NanoSTL https://github.com/lighttransport/nanostl
* STB(load/save image) https://github.com/nothings/stb
* ImGui(GUI) https://github.com/ocornut/imgui
* Nuklear(GUI) https://github.com/vurtun/nuklear
* JSON for Modern C++ https://github.com/nlohmann/json
* TinyObjLoader(Wavefront .obj loader) https://github.com/syoyo/tinyobjloader
* TinyEXR(OpenEXR library) https://github.com/syoyo/tinyexr
* TinyDNGLoader(DNG RAW library) https://github.com/syoyo/tinydngloader
* window-bootstrap(Cross-platform C++ Window/UI bootstrap) https://github.com/syoyo/window-bootstrap
* Catch(Unit test framework) https://github.com/catchorg/Catch2
* Civetweb(http server) https://github.com/civetweb/civetweb
* spdlog(logging) https://github.com/gabime/spdlog

EoL.
