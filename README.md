# FISHPACK-CMake

This repository is a fork of UCAR's [FISHPACK Fortran 77 library 4.1](https://www2.cisl.ucar.edu/resources/legacy/fishpack) with added CMake support. All changes are non-breaking and users can still build FISHPACK with the original Makefiles.

For more information and installation using the original Makefiles, see [README_FISHPACK4.1](doc/README_FISHPACK4.1).


## Build instructions

### Prerequisites
The following software are required to build FISHPACK-CMake from source:

- Linux or macOS
- Intel or GNU Fortran compiler
- [CMake](https://git-scm.com/) version 3.0, or above
- [Git](https://git-scm.com/) (_Optional_ if cloning)


### Download

Clone or download FISHPACK-CMake from the GitHub repository at https://github.com/dmey/fishpack-cmake.

### Build and tests

Go into `fishpack-cmake` and run the following commands from your command-line interface:

```sh
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -DUSE_REAL8=ON -DTESTS=ON ..
make # Creates shared and dynamic library
ctest # Run tests
```

## Support

Please note that FISHPACK-CMake is not being actively developed or supported.

## Copyright
FISHPACK, Copyright (C) 2004-2011, Computational Information Systems Laboratory, University Corporation for Atmospheric Research.

CMake support, Copyright (C) 2019, D. Meyer.

## License

```
Copyright © 2004 the University Corporation for Atmospheric Research ("UCAR"). All rights reserved. Developed by NCAR's Computational and Information Systems Laboratory, UCAR.

Redistribution and use of the Software in source and binary forms, with or without modification, is permitted provided that the following conditions are met:

Neither the names of NCAR's Computational and Information Systems Laboratory, the University Corporation for Atmospheric Research, nor the names of its sponsors or contributors may be used to endorse or promote products derived from this Software without specific prior written permission.
Redistributions of source code must retain the above copyright notices, this list of conditions, and the disclaimer below.
Redistributions in binary form must reproduce the above copyright notice, this list of conditions, and the disclaimer below in the documentation and/or other materials provided with the distribution.
THIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE CONTRIBUTORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS WITH THE SOFTWARE.

FISHPACK is a product of the Computational & Information Systems Laboratory at the National Center for Atmospheric Research (NCAR)
```