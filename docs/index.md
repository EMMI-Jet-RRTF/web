![EMMI Logo](https://www.gsi.de/fileadmin/_processed_/4/d/csm_Emmi_logo_web_2aa7dc5b12.png)

## [ExtreMe Matter Institute](https://www.gsi.de/work/wissenschaftliche_netzwerke/helmholtz_allianz_emmi.htm) 

# Rapid Reaction Task Force: The space-time structure of jet quenching - theory and experiment

## Computing, Datasets, Software

- Indico page for RRTF: [https://indico.gsi.de/event/8938/](https://indico.gsi.de/event/8938/)
- This github page [https://hotqcd.github.io/emmi-jet-rrtf/](https://hotqcd.github.io/emmi-jet-rrtf/)
- Link to github repository [https://github.com/hotqcd/emmi-jet-rrtf](https://github.com/hotqcd/emmi-jet-rrtf)

## Instructions on GSI cluster use

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
   > ssh -l <username> -N -L 2222:kronos.hpc:22 lx-pool.gsi.de
   ```
   
   3. in another shell (if ssh tunnel process not sent to background) use rsync to copy files or directories via the ssh tunnel
   ```
   > rsync -avh --progress -e "ssh -l <username> -p 2222" test.file localhost:~/
   ```

## Software

Under construction

## Data sets

Under construction

## Other Links
- [JetTools 2019](https://indico.cern.ch/event/771644/overview)
- [JETSCAPE Collaboration](http://jetscape.org/)

