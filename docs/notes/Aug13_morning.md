# Discussion notes Aug 13 morning

## Plot formatting

Agree on a common set up for Lund and EMMI plots: observables, scaling, formatting
   * normalize per jet
   * logarithmic z-scale
   * label of each figure should fully decsribe content
   * same dynamic range for all plots (both RHIC and LHC)

Definitions:
   * kt = DeltaR * pTsub2
   * z = pTconst/pTjet
   * DeltaR = sqrt(Delta_y^2 + Delta_phi^2) (Fastjet definition)
   * theta: angle between jet axis and constituent
   
Lund: 
   * vertical axis: ln(kt/GeV)
   * vertical axis dynamic range: [-3, 6] 
   * horiz axis: ln(1/DeltaR)
   * horiz axis: ln(1/theta)
   * horiz axis dynamic range: [0,8] 
   
EMMI:
   * vertical axis: ln(1/z)
   * vertical axis dynamic range: [0,10]
   * horiz axis: ln(1/DeltaR)
   * horiz axis: ln(1/theta)
   * horiz axis dynamic range: [0,8]
   
## Comments on EMMI diagrams

Most useful is the difference plot AA - pp
   * needs sufficient statistical precision - do we have that?
   
Study effects of hadronization: 
   * look at difference plot PYTHIA-Herwig for pp collisions

## Common jet kinematics 

Inclusive jets:
   * RHIC: pTjet>15, 40 GeV (pThat=10, 35), \|eta_jet\|<1
   * LHC: pTjet>70, 350 GeV (pThat=50, 300 GeV), \|eta_jet\|<2
   
Gamma+jet:

   * RHIC:
      ** \|delta_phi – pi\| < 0.6
      ** pTgamma > 20 GeV
      ** choose hardest recoil jet with pTjet > 10 GeV
      
   * LHC:
      ** \|delta_phi – pi\| < 0.6
      ** pTgamma > 100 GeV
      ** choose hardest recoil jet with pTjet > 30 GeV

Alternative to fix initial kinematics: read initial parton energy from HEPMC record
   * also use to separate q/g?
   
   

