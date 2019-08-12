## JETSCAPE

The following JETSCAPE samples are available:
- pp
- MATTER + LBT, 0-5%, 30-40%
- MATTER + Martini, 0-5%

**Location**: `/lustre/emmi/emmi02/jetscape`

Files are labeled `model_sqrts_(centrality)_pthat_HadronizationType`

For AA, use "colorless" hadronization. For pp, use either "colored" or "colorless".

(production ongoing...)

**Format**: HepMC 3.1.1

**System**: Pb-Pb 2.76 TeV

**Process**: Di-jet 

**pt-hat bins**: > 50 GeV, > 300 GeV (one hard scattering per event)

**Parton shower history**: encoded in HepMC graph

**Hydro**: event-averaged VISHNU (2+1)D

**Medium response**: Encoded in HepMC graph for MATTER+LBT, none for MATTER+Martini

**Statistics**: ~500k pp, ~100 Pb-Pb each

Detailed configuration settings can be found in each subdirectory.

JETSCAPE Manual: https://arxiv.org/abs/1903.07706

Note that these are not official tuned settings, but rather some reasonable guess -- use appropriate caution. 


<hr>

Contact: James Mulligan
