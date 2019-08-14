## "Saclay" model

**General description**: parton shower including modifications of the phase space for vacuum-like emissions due to the dense medium, decoherence and medium-induced mini-jets.

**Model**: This parton shower evolves an initial parton coming from the hard scattering according to the following three steps:

(1) firstly, an angular ordered vacuum-like shower inside the medium, with running coupling and full DGLAP splitting functions.
The inside region is defined in the phase space by kt^2>sqrt(qhat omega) (equivalently omega/kt^2 < sqrt(omega/qhat)) and theta> theta_coherence. At leading logarihmic accuracy, vacuum like emissions are angular ordered inside the medium (despite quantum color decoherence).

(2) once the previous shower has reached the in-medium cut, all the sources trigger medium-induced cascades during time L (fixed length of the medium). The strong coupling constant is fixed to the free parameter alphas_med during this step.

(3) finally the previous sources are further evolved outside the medium (formation time > L) as in the vacuum until the hadronization cut, without any constraint on the angle of the first emission outside because of decoherence. 

The medium is simply a "brick" of QGP. Three parameters: qhat, L, and alphas_med. No hadronization. No UE.

See arXiv:1801.09703 for the general picture and arXiv:1907.04866 (section 3) for the details of the MC implementation.

**Data samples**:

- final state events at parton level only, with 1 million events.

- available at /lustre/emmi/emmi21/saclay-model/data-samples/ in hepmc format.

- files 'saclay-model-dijet_pthat{pthat}-vacuum.hepmc' for the pp baseline with pthat = 50 GeV or 300 GeV.

- files 'saclay-model-dijet_pthat{pthat}-medium_{qhat_L_alphas_med}.hepmc' for the full medium shower with qhat = 1.5 GeV^2/fm, L = 4 fm, alphas_med = 0.24 (set of parameters reproducing the experimental R_AA ratio for jets.)

<hr>

Contact: Paul Caucal
