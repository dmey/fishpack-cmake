# FISHPACK-CMake (https://github.com/dmey/fishpack-cmake).
# Copyright (C) 2019 D. Meyer.

set(testsrc tblktri.f tcblktri.f tcmgnbn.f tgenbun.f
        thstcrt.f thstcsp.f thstcyl.f thstplr.f
        thstssp.f thw3crt.f thwscrt.f thwscsp.f
        thwscyl.f thwsplr.f thwsssp.f tpois3d.f
        tpoistg.f tsepeli.f tsepx4.f
)

# Create separate executables for each test
foreach(fpath ${testsrc})
    get_filename_component(fname ${fpath} NAME_WE)
    add_executable(${fname} "${fname}.f")
    target_link_libraries(${fname} fishpack_shared)
    add_test(${fname} ${fname})
endforeach()