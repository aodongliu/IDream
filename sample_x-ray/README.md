To calculate X-ray spectroscopy, there are 2 ways: Linear response TDDFT and Multi-reference configuration interaction.

1. They both require a SCF calculation as the start (to read MO from). Therefore, first step is to do a SCF calculation with the optimized geometry.

2. For LRTDDFT:
    a) define %oldchk to be the previous SCF calculation
    b) td=(nstates=100,demin=1546000,full) guess=read geom=checkpoint
       (full here is to make sure Gaussian is not doing frozen orbital approximation)
    c) Results: search "Excited State" to read energy and oscillator strength

   For multi-reference CI:
    Need to use l910 in our group. More intro about l910 and IOps can be found on ligroupWiki
    a) define %oldchk to be the previous SCF calculation
    b) run a CASSCF caculation to get better orbitals, see sample input CAS.gjf
    c) run a RASCI calculation which includes 1s orbitals in RAS1 and the valence in the RAS2 (CAS), RAS3 may be empty. Remember Energy Specific Davidson to set a proper threshold. see sample RAS.gjf
    d) Results (state energies and corresponding oscillator strength) will be printed out 



