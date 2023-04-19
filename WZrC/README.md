## FitSNAP3 Tungsten Zirconium Carbide potential

These files will generate a potential for WZrC as described in arXiv:2212.01432 and J. Chem. Phys(https://doi.org/10.1063/5.0135269). This potential is optimized for bulk and surface structures for both W and ZrC. No optimization was performed on pure C structures, and no physical performance should be expected for pure C simulations. We expect the potential to perform well in the temperature range of 300 - 2500K. Primary optimization was performed on bulk modulus, (100) and (110) surface energies, thermal expansion, and several stability checks detailed in the manuscript.

#### Files in this directory
WZrC.in
Input file that contains the parameters to run FitSNAP to generate the WZrC potential

JSON/
Directory that contains all the training configurations which are organized into different groups

WZrC_pot.mod
File that should be included in a lammps input script to use the WZrC potential. This file includes the reference zbl potential used to fit the WZrC potential. Running the potential without these zbl parameters will likely not result in the reported properties and performance.

#### Files generated after running FitSNAP 

WZrC_pot.snapcoeff
SNAP potential coefficient file that contains all the coefficients for this potential. This is one of the files needed to use this potential in lammps.

WZrC_pot.snapparam
SNAP potential parameters file that contains hyperparameters and options used during the fit for this potential. This is one of the files needed to use this potential in lammps.

WZrC_metrics.csv
Contains error metrics for all the training groups in this fit.

19Apr23_Standard/ contains output from running this fit. Users may use the included WZrC_pot.snapcoeff, WZrC_pot.snapparam, and in.snapWZrC files for lammps simulations without needing to rerun FitSNAP.

#### Notes
The energy and force weights were optimized in Dakota as 10^(group weight). This is why, for example, the ground state energy weight is given as 7.32 in Table I, but is given in the FitSNAP input file as 21129420.31. 

Previous files contained in 09Jan23_Standard/ were erroneous due to a now solved bug. The files in 19Apr23_Standard/ are now in agreement with those generated in the original Dakota run.
