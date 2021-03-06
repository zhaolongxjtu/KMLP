The KMLP package adds a pair_stype ml/energy command which computes interatomic interactions for K liquid or solid system.
More detailed information about this potential can be found in the doc/pair_ml_energy.txt

== Installation of the KMLP package ==

Instructions for compiling LAMMPS + KMLP using  the traditional Makefile approach is given in KMLP_CODE/README.txt. 
Necessary files are included in the make directory, respectively.

== Documentation ==

A description of parameters and files necessary to run LAMMPS with KMLP are in doc/pair_ml_energy.txt

== Run tests ==

Sample LAMMPS input files which use the KMLP are included in the example directory. These files are:

*Standard LAMMPS files

1. in.lammps - LAMMPS input file using the ml/energy pair style

*KMLP files
2. Param_ML_pot.txt - File containing fitted parameters for the potential. 

To run the example:
	cd example
	lmp -in in.lammps 

== Credits and license ==

This compute was written by H Zong (zonghust@mail.xjtu.edu.cn) and is licensed under the GPLv2 license.

Please contribute changes back to the community.

