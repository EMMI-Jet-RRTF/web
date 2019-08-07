![EMMI Logo](https://www.gsi.de/fileadmin/_processed_/4/d/csm_Emmi_logo_web_2aa7dc5b12.png)

## [ExtreMe Matter Institute](https://www.gsi.de/work/wissenschaftliche_netzwerke/helmholtz_allianz_emmi.htm) 

# Rapid Reaction Task Force: The space-time structure of jet quenching - theory and experiment

# Table of Contents
1. [Workshop Links](#WorkshopLinks)
2. [Software](#Software)


# Workshop Links <a name="WorkshopLinks"></a>

- Workshop indico page: [https://indico.gsi.de/event/9270/](https://indico.gsi.de/event/9270/)

- Open symposium (Monday morning): [https://indico.gsi.de/event/9065/](https://indico.gsi.de/event/9065/)

- This github page [https://hotqcd.github.io/emmi-jet-rrtf/](https://hotqcd.github.io/emmi-jet-rrtf/)
- Link to github repository [https://github.com/hotqcd/emmi-jet-rrtf](https://github.com/hotqcd/emmi-jet-rrtf)

# Instructions on GSI cluster use

* IT help at GSI: contact Carsten Preuss (<c.preuss@gsi.de>) and Thomas Roth (<T.Roth@gsi.de>)

* For a workshop account on the GSI HPC facility contact Peter Jacobs, who will assign you a unique guest account (refered to here as \<username\>).

* To log on to the facility:

```
From your machine:
> ssh <username>@lx-pool.gsi.de

Then from the gateway node
> ssh kronos.hpc
```
* Documentation for batch system: [Slurm@Kronos](https://wiki.gsi.de/foswiki/bin/view/Linux/SlurmUsage)
   * Dedicated cpu: 300 cores
   * job submission: use `sbatch --reservation=emmi_85 ....`

* Storage: every guest account has a dedicated area for several TB of storage at `/lustre/emmi/<username>`, which is accessible from the kronos.hpc nodes

* Using software which is not system-standard (e.g. new compiler):

```
module use /cvmfs/it.gsi.de/modulefiles/
module avail
module use
```

* Copying files generated externally directly to kronos.hpc:
   1. Set up ssh pub-key authentication - no pass typing
   
   2. open an ssh tunnel (and keep it open):
   ```
   ssh -l <username> -N -L 2222:kronos.hpc:22 lx-pool.gsi.de
   ```
   
   3. in another shell (if ssh tunnel process not sent to background) use rsync to copy files or directories via the ssh tunnel
   ```
   rsync -avh --progress -e "ssh -l <username> -p 2222" test.file localhost:~/
   ```

# Software <a name="Software"></a>

Under construction

# Data sets

Here is the dataset link: [datasets](datasets.md)


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

# Other Links
- [JetTools 2019](https://indico.cern.ch/event/771644/overview)
- [JETSCAPE Collaboration](http://jetscape.org/)

