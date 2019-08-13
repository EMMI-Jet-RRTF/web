# Discussion notes Aug 13 morning

## Plot formatting

Agree on a common set up for Lund and EMMI plots: obsrevables, scaling, formatting
   * normalize per jet
   * logarithmic z-scale
   * label of each figure should fully decsribe content
   * same dynamic range for all plots (both RHIC and LHC)

Lund: 
   * vertical axis: log(kt/GeV)
   * vertical axis dynamic range: [-3, 5]  (??)
   * horiz axis: log(1/$\Delta${R})
   * horiz axis dynamic range: [0,6] (??)
   
EMMI:
   * vertical axis: log(1/z)
   * vertical axis dynamic range: [0,10] (??)
   * horiz axis: log(1/$\Delta${R})
   * horiz axis dynamic range: [0,6] (??)
   
## Comments on EMMI diagrams

Most useful is the difference plot AA - pp
   * needs sufficient statistical precision - do we have that?
   
Study effects of hadronization: 
   * look at difference plot PYTHIA-Herwig for pp collisions

## Common jet kinematics 

Inclusive jets:
   * RHIC: pTjet>15, 40 GeV (pThat=10, 35 GeV); |eta_jet|<1
   * LHC: pTjet>70, 350 GeV (pThat=50, 300 GeV); |eta_jet|<2

Gamma+jet:
   * |delta_phi – pi| < 0.6
   * pTgamma > 100 GeV
   * choose hardest recoil jet with pTjet > 30 GeV

Fix initial kiematics: read initial parton energy from HEPMC record
   * also use to separate q/g?
   
   

