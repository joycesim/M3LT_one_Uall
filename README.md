# M3LT_one_Uall

Two phase flow models applied to mid-ocean ridges

This suite of models accompany the paper submitted to PEPI-LAB.

To run all six models presented in the paper:
1) Build TerraFERMA (https://terraferma.github.io/) 
2) Build and run models using [tfsimulationharness --run ridgemodel.shml].

The models span two parameters:
1) Half spreading rates, U_0 = 2,4,8 cm/yr
2) Intrinsic permeability, K_0 = 4e-7, 4e-9 m2.  

The models are one-way coupled such that the the solid half is solved once at the beginning, then the fluid is solved at every time step.
