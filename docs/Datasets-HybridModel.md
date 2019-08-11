## Hybrid Model

### Output
HepMC3 files in /lustre/emmi/emmi07/hybrid_datasets<br/>
The name of the folder describes the parameters of the simulation:<br/>
* *rhic_200* or *lhc_5020*
* *pp* or *05* or *5060*
* *phot_X* or *dijet_X*, where *X* describes the value of pt_hat_min of the simulation

Inside folders *05* and *5060* there are two files:
* *kappa0p404.dat*, results with quenching, with kappa_sc=0.404.
* *noquench.dat*, results without quenching

The purpose of the unquenched results is to be able to compare against quenched ones event by event, where the PDFs are the same. One can also use the *noquench.dat* results to estimate the effect of nPDFs. <br/>
In order to get a pp reference one needs to look at *pp* folders.

* Headers

  * __U GEV MM__<br/>
   All units in GeV and mm.

  * __W 1.0000000000000000000000e+00__<br/>
   Event pt_hat weight.<br/>
   All weights = 1 trivially for these runs with fixed pt_hat.

  * __A 0 GenCrossSection 4.87142535e+03 4.87142535e+03 -1 -1__<br/>
   Hard cross section (different in pp and PbPb due to nPDF).<br/>
   cross_section and cross_section_error in position 1 and 2 in the line.<br/>
   Two last integers are irrelevant.

  * __A 0 GenPdfInfo 0 0 1.22000454e-12 5.57096735e-12 0.00000000e+00 0.00000000e+00 0.00000000e+00 0 0__<br/>
   Not really PDF info.<br/>
   I use this line to write the creation point in (x,y) plane of hard scattering, in mm, in position 3 and 4 in the line. In this example:<br/>
   x=1.22000454e-12<br/>
   y=5.57096735e-12<br/>
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

<hr>

Contacts: Daniel Pablos
