# DynaRoot

This branch includes HRLDAS/Noah-MP v4.5-WRF with a dynamic root scheme that simulates deep root water uptake. See [Fan et al. (2017)](https://doi.org/10.1073/pnas.1712381114) for details on the root scheme. This version of the model also includes additional resolved soil layers and soil properties which vary with depth according to an exponential decay function ([Miguez-Macho and Fan 2012](https://doi.org/10.1029/2012JD017539)). 

Please contact Carolina Bieri (cab478@ucar.edu) with any questions about the code in this repository.

Please see the accompanying publication ([Bieri et al. 2025](https://doi.org/10.5194/gmd-18-3755-2025)) for information on the development of this version of HRLDAS/Noah-MP. 

Running this version of HRLDAS/Noah-MP is similar to running [version 4.5](https://github.com/NCAR/hrldas/tree/release-v4.5-WRF). However, there are a few changes to namelist options and output variables.

This version adds a namelist option that activates the DynaRoot scheme: 
```
ROOT_OPTION = 2
```
The default option is 1 (DynaRoot not activated). Set to 2 to activate DynaRoot.

Also, this version adds output variables associated with the DynaRoot scheme.

- **EASY:** Root scheme ease function (real, unitless)
- **ROOTACTIVITY:** Root activity (real, unitless)
- **KROOT:** Layer depth of root zone (integer, unitless)
- **KWTD:** Layer depth of water table (integer, unitless)
- **INACTIVE:** Number of timesteps with inactive roots (integer, unitless)
- **GWRD:** Root water uptake depth (integer, unitess)
