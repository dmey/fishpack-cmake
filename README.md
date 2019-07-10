# FISHPACK-CMake

This repository is a fork of UCAR's [FISHPACK Fortran 77 library 4.1](https://www2.cisl.ucar.edu/resources/legacy/fishpack) with added CMake support. All changes are non-breaking and users can still build FISHPACK with the original Makefiles.
For more information and installation using the original Makefiles, see the [official website](https://www2.cisl.ucar.edu/resources/legacy/fishpack).


## Build

```sh
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -DTESTS=ON ..
make # Creates shared and dynamic library
ctest # Run tests
```

## Copyright and license

FISHPACK, Copyright (C) 2004-2011, Computational Information Systems Laboratory, University Corporation for Atmospheric Research

For CMake support, Copyright (C) 2019, D. Meyer.

See [LICENSE](LICENSE) for licensing information.