# M3LT_one_Uall

Two phase flow models applied to mid-ocean ridges

This suite of models accompany the paper:
Sim, S. J., Spiegelman, M., Stegman, D. R., & Wilson, C. (2020). The influence of spreading rate and permeability on melt focusing beneath mid-ocean ridges. Physics of the Earth and Planetary Interiors, 304, 106486. https://doi.org/10.1016/j.pepi.2020.106486

To run all six models presented in the paper:
1) Build TerraFERMA (https://terraferma.github.io/) 
2) Build and run models using `tfsimulationharness --run ridgemodel.shml`.

The models span two parameters:
1) Half spreading rates, U_0 = 2,4,8 cm/yr
2) Intrinsic permeability, K_0 = 4e-7, 4e-9 m2.  

The models are one-way coupled such that the the solid half is solved once at the beginning, then the fluid is solved at every time step.

## MacOS (M1 chip)

go to [Mitchel's notes on how to install on windows](https://github.com/mitchellmcm27/terraferma-notes)

Download & install XQuartz

Open XQuartz preferences, go to Security tab, check "Allow connections from network clients" (only needs to be done once)

Restart or quit XQuartz

`xhost +localhost`

`docker run -it -e DISPLAY=host.docker.internal:0 -v /tmp/.x11_unix:/tmp -v $PWD:/home/tfuser/shared terraferma/dev`

Inside the container

`sudo chown -R tfuser /tmp`

Note: it seems that mapping the volume -v /tmp/.x11_unix:/tmp may not be necessary (diamond GUI still works), in which case it is also not necessary to sudo chown -R tfuser /tmp inside the container.
