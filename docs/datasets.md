# Data sets

## Hydro

Smooth hydro profiles are available at: `/lustre/emmi/emmi02/hydro`
(Thanks to Chun Shen!)

There is a folder each for AuAu@200 GeV, PbPb@2.76 TeV, and PbPb@5.02 TeV. 
Centrality bins span from 0-5% to 70-80%.

The files are generated using MCGlauber initial condition with VISH2+1 (no hadronic afterburner). The hydrodynamic simulations were done with s95p-v1-PCE150 EoS with a partial chemical equilibrium temperature at 150 MeV. The kinetic freeze-out was at 105 MeV to match the slops of single particle spectra.

For the initial binary collision profiles, they are stored in the initial_conditions/ folder and named rho_binary_fromSd_order_2_CXXX.dat. Each of these files stores a 301x301 matrix which represents the binary density profile in the transverse plane with -15 to 15 fm grid size and dx = dy = 0.1 fm grid spacing.

Please cite https://arxiv.org/pdf/1806.05288.pdf for the simulation setup. 
Fig. 5 shows the quality of the agreement with experimental data. 

## PYTHIA
## HERWIG
## JETSCAPE
## JEWEL
## MARTINI
## Hybrid Model
## Q-PYTHIA

<hr>

[Back to EMMI-Jet-RRTF](index.md)
