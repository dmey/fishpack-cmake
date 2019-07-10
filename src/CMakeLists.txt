# FISHPACK-CMake (https://github.com/dmey/fishpack-cmake).
# Copyright (C) 2019 D. Meyer.

set(libsrc blktri.f cblktri.f cmgnbn.f comf.f
        fftpack.f genbun.f gnbnaux.f hstcrt.f
        hstcsp.f hstcyl.f hstplr.f hstssp.f hw3crt.f
        hwscrt.f hwscsp.f hwscyl.f hwsplr.f hwsssp.f
        pois3d.f poistg.f sepaux.f sepeli.f sepx4.f
)

# Use "object libraries" to avoid the duplicated compilation
# of the object files (https://stackoverflow.com/a/29824424).
# This is the "object library" target: compiles the sources only once
add_library(objlib OBJECT ${libsrc})

# Shared libraries need PIC
set_property(TARGET objlib PROPERTY POSITION_INDEPENDENT_CODE 1)

# Shared and static libraries built from the same object files
add_library(fishpack_shared SHARED $<TARGET_OBJECTS:objlib>)
add_library(fishpack_static STATIC $<TARGET_OBJECTS:objlib>)