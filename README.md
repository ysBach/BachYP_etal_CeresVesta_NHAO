# Bach et al. (2024a, b) Archive

This is a repository to archive the **results** (but not all the required data; see the note below) from the codes, used in the following papers:
* **Paper1**: Bach et al. (2024a) A&A, in press
* **Paper2**: Bach et al. (2024b) A&A, under review

If you need the raw data, refer to 10.5281/zenodo.7788352 as indicated in Paper2.
(will be open to public as soon as Paper 2 is officially accepted)

## Important Notes
Unfortunately, I cannot open all the data I used in the papers. Hence:

* ⚠️**IMPORTANT**: The codes will **NOT** run perfectly on your machine.
  * Because not all files are included in this repo.
  * Because (1) I am not the copyright holder and/or (2) original data is too large.
* Important raw data are accessible from Zenodo above.

Some parts will give, e.g., ``FileNotFoundError``, so as noted, the codes will fail if you run them without any modification.


## Contents

In ``codes_n_data`` directory:
* ``<YYYYMMDD>_<OBJNAME>.ipynb``: The reduction process for each object.
  * ``sky``: The blank sky frames we took to test dome flat
  * ``SP``/``UP``: Strongly Polarized and UnPolarized standard star exposures.
  * Especially using SP/UP/sky data, I spent 2 years for developing ``NICpolpy`` ([GitHub](https://github.com/ysBach/NICpolpy); published [Bach+2022 SAG](https://ui.adsabs.harvard.edu/abs/2022arXiv221214167B/abstract)). The files that I did not include in the repo (too dirty code) are:
    1. Finding the best algorithm to remove instrument artifacts (especially the Fourier pattern)
    2. Checking for bad pixels and possible uncertainties by preprocessing steps (including errors in flat, dark current, artifacts, and cosmic-ray rejection).
    3. Re-calibrating instrument parameters (gain and readout noise) and statistical testing to check whether there are pixel-to-pixel variations.
    4. Finding the best algorithm to remove the sky fringe patterns and quantify the possible errors (Bach et al. 2024, in prep)
    5. There are many more parts related to instrument artifacts, finding the best algorithm for object centering, statistical analyses, etc.
* ``_phot.ipynb``/``_polr.ipynb``: The (dirty) notebooks I used to do photometry and polarimetry, using multiple `apmode`, outlier, and other parameters (see Appendix A/B of Paper2).
  * Because of extensive testing, many parts are commented out, unused, and/or used in different orders.
* ``figures-01-CeresVesta.ipynb``: The code to plot PPCs in Paper2. Also it makes the final result as ``restuls/df_fit_all.csv``. Some cells are deleted.
* ``figures-part1.ipynb``: The code to plot multiple PPC-related parameters (``figs/``). Multiple cells are deleted before adding here.

In ``codes_n_data/results`` directory:
* ``figs/``: The PPC and $q$-$u$ plane plots to see the data scatter depending on the algorithms (Appendix of Paper2).
* ``figs-mcmc``: The final PPC and MC (Monte Carlo) simulation corner plots (Paper2 Appendix C)
* ``figs-time``: The time-variation of the polarization degree (not included in Paper2)
* ``<OBJNAME>_<OBSDATE>_<rapmode>.csv``: The aperture radius and q/u-related parameters for multiple algorithms (Appendix of Paper2)
* ``df_fin.csv``: Extracted only the final results
* ``df_fit_all.csv``: All the fitted results after MC simulation

In ``codes_n_data/extdata`` directory:
* A dirty collection of external data from other sources, excluding those I have no right to open to the public. I had to remove some columns in some files, including ``all_samples.xlsx`` (which does not include *all* the samples, unlike its name says...).
* For PPCs that should be fitted to obtain polarimetric parameters, I am planning on (but cannot guarantee) uploading my codes and results at a [separate repo](https://github.com/ysBach/ppc_fit_archive).


In ``codes_n_data/figs`` directory:
* Results from ``figures-part1.ipynb`` (figures used for Paper1).


## History of Submission
Times in KST (GMT+0900)
* 2023-08-28: Submission of the paper (initially Paper1&2 were designed to be a single paper)
* 2023-09-11: Received Referee comment #1.
* 2023-12-12: Splitted the manuscript into two and submitted (based on referee's comment).
* 2023-12-22: Received Referee comment #2 for both papers (minor revision). Editorial office recommended English proofread.
* 2024-01-08: Resubmission of the manuscript after English proofread (AJE).
* 2024-01-08: Paper 1 accepted.
* 2024-01-10: Paper 1 minor language revision.