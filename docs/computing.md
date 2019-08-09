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

<hr>

[Back to EMMI-Jet-RRTF](index.md)
