# Analysis Software [emmi-jet-rrtf](index.md)

<hr>

# FASTJET, HEPMC, LHAPDF, PYTHIA with python - HepPy

- [https://github.com/matplo/heppy](https://github.com/matplo/heppy)
- installed at GSI in emmi01 user dir

## load the modules
```
module use /u/emmi01/rrtf/heppy/modules
module load heppy/main_python
```

- see what's loaded
```
module list
```

## try examples

- note: examples use a progress bar - run the command below
```
pip install tqdm --user
```

- also rather soon you will need numpy and pandas
```
pip install numpy pandas --user
```

### generate some pythia events and on-the-fly run fastjet, de-cluster into Lund, soft-drop ...

```
/u/emmi01/rrtf/heppy/examples/pythia_gen_fastjet_lund_test.py
```

- code on github: [https://github.com/matplo/heppy/blob/master/examples/pythia_gen_fastjet_lund_test.py](https://github.com/matplo/heppy/blob/master/examples/pythia_gen_fastjet_lund_test.py)

### generate some pythia events and write a hepmc2 file

```
/u/emmi01/rrtf/heppy/examples/pythia_gen_write_hepmc.py
```

   - code on github: [https://github.com/matplo/heppy/blob/master/examples/pythia_gen_write_hepmc.py](https://github.com/matplo/heppy/blob/master/examples/pythia_gen_write_hepmc.py)

### read the hepmc2 file and run a jet finder....

- note for this step you will need an extra package - one time command...

```
pip install pyhepmc_ng --user
```

- now run the jet finding on the hepmc file:

```
/u/emmi01/rrtf/heppy/examples/hepmc_jetreco.py --hepmc 2 -i ./pythia_gen_test_hepmc2.dat
```

   - code on github: [https://github.com/matplo/heppy/blob/master/examples/hepmc_jetreco.py](https://github.com/matplo/heppy/blob/master/examples/hepmc_jetreco.py)

- or run on jetscape events, and save a ROOT histogram:

```
/u/emmi01/rrtf/heppy/examples/hepmc_jetscape_jetreco.py -i /lustre/emmi/emmi02/PP19_2760_50_dijet/1/test_out.hepmc
```
   - code on github [https://github.com/matplo/heppy/blob/master/examples/hepmc_jetscape_jetreco.py](https://github.com/matplo/heppy/blob/master/examples/hepmc_jetscape_jetreco.py)

### more items coming up...
