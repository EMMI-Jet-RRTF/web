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

### Output
* Headers

  * __U GEV MM__
   All units in GeV and mm.

  * __W 1.0000000000000000000000e+00__
   Event pt_hat weight.
   All weights = 1 trivially for these runs with fixed pt_hat.

  * __A 0 GenCrossSection 4.87142535e+03 4.87142535e+03 -1 -1__
   Hard cross section (different in pp and PbPb due to nPDF).
   cross_section and cross_section_error in position 1 and 2 in the line.
   Two last integers are irrelevant.

  * __A 0 GenPdfInfo 0 0 1.22000454e-12 5.57096735e-12 0.00000000e+00 0.00000000e+00 0.00000000e+00 0 0__
   Not really PDF info.
   I use this line to write the creation point in (x,y) plane of hard scattering, in mm, in position 3 and 4 in the line. In this example:
   x=1.22000454e-12
   y=5.57096735e-12
   Rest of numbers are irrelevant.

* Particle List

Parton status | Meaning
--------------|--------
23 | Parton outgoing from the hard scattering (two per event).
41 | Parton originating from ISR undergoing FSR.
62 | Beam remnant (does not get quenched, stored for color flow purposes in Lund fragmentation).
3 | Any other parton not belonging to previous categories.

Hadron status | Meaning
--------------|--------
1 | Stable hadron coming from Lund string fragmentation of not completely quenched partons.
6 | Hadron coming from the wake, ridge contribution ("positive" back-reaction particle).
7 | Hadron coming from the wake, trough contribution ("negative" back-reaction particle).

__Genealogy Logic__

_Partons_:
* Full parton shower history kept in file:
  * Only time-like shower information, or FSR.
  * No record of incoming hard partons.
  * No record of ISR shower.
  * To know the starting space-time position of partons with status 23 and 41, one needs to look at GenPdfInfo line for (x,y) creation point in transverse plane, with z=t=0. Therefore, all partons with status 23 and 41 have the same starting space-time position.
          
* Vertex line contains space-time position of partonic splitting, as (x,y,z,ct), in mm.

* To study parton level jets, one has to find the partons who are not mothers of any other partons.

_Hadrons_:
* No info about Lund fragmentation process nor decay processes is kept. All hadrons with status 1 are thus motherless. Of course, one can still match parton jets to hadrons jets through the usual angular matching criteria.

* Hadrons from the wake, with status 6 and 7, have as a mother the final parton that sourced them. (This means that a final parton can be a mother of a hadron, but still is to be considered final because it is not a mother of a parton).

### Misc

__Analysis__

* "positive" back-reaction particles are to be treated at equal footing with stable hadrons with status 1.
* "negative" back-reaction particles are to be treated with weight=-1 in histograms, and their energy and momentum is to be subtracted from the energy and momentum of the jets they fall into.

__Hadronization__

* pi0s are not allowed to split, and are considered stable.

### The model
Under construction

## Q-PYTHIA

<hr>

[Back to EMMI-Jet-RRTF](index.md)

