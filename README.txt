== Building LAMMPS with the KMLP code ===

LAMMPS + KMLP can be built using the traditional makefile build system. Instructions for this approache is included here (make directory, respectively).

Regardless of compilation method, the user will need a stable release of LAMMPS 
(https://lammps.sandia.gov/) as well as the dlib c++ library (http://dlib.net/). 
They can be downloaded either as a tarball or using git:

* LAMMPS:
git clone -b stable https://github.com/lammps/lammps.git

* DLIB:
git clone https://github.com/davisking/dlib.git

== MAKE ==

To compile LAMMPS + KMLP with the traditional makefile approach, the dlib library must 
be compiled separately and linked with LAMMPS. 

To compile LAMMPS + KMLP with make:

1. Compile dlib using the following commands: 
	cd dlib/examples
	mkdir build
	cd build
	cmake ..
	cmake --build . --config Release

2. Add dlib to library path:
	export LIBRARY_PATH=/path/to/dlib/examples/build/dlib_build
	
3. Edit MAKE/Makefile.KMLP so that /path/to/dlib on line 51 is your actual path. Then copy 
Makefile.KMLP into lammps/src/MAKE/MINE.

4. Copy pair_ml_energy.cpp, pair_ml_energy.h, Makefile.lib and style_pair.h into lammps/src. 

5. Compile LAMMPS with the desired packages. See https://lammps.sandia.gov/doc/Build_package.html 
for information about installing packages with make.
	cd /path/to/lammps/src
	make [yes-pkg]
	make KMLP

This will yield the executable lammps/src/lmp_KMLP.


	
