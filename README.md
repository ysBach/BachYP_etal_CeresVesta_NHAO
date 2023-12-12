# Ceres Vesta NHAO

This is a repository to archive the codes and data used in the following papers:
* Bach et al. (2023a) A&A, under review
* Bach et al. (2023b) A&A, under review

## Important Notes
Unfortunately, I cannot open all the data I used in the papers (e.g., filter throughput). Hence:

* **IMPORTANT**: The codes will **NOT** run perfectly on your machine.
* Because not all files are included in this repo.
* Because I am not the copyright holder.

Some parts will give, e.g., ``FileNotFoundError``. Therefore, I did not put much effort into complete documentation for perfect reproducibility. I was also a bit nervous any change I make to these files will result in different results from the publications. However, if you have a general understanding of Python and the widely used packages (versions as of 2023), you can understand what I did by looking into the codes.


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
* ``_phot.ipynb``/``_polr.ipynb``: The (dirty) notebooks I used to do photometry and polarimetry, using multiple `apmode`, outlier, and other parameters (see Appendix A/B of Bach et al. 2023b).
  * Because of extensive testing, many parts are commented out, unused, and/or used in different orders.
* ``figures-01-CeresVesta.ipynb``: The code to plot PPCs in Bach+23b. Also it makes the final result as ``restuls/df_fit_all.csv``. Some cells are deleted.
* ``figures-part1.ipynb``: The code to plot multiple PPC-related parameters. Multiple cells are deleted before adding here.

In ``codes_n_data/results`` directory:
* ``figs/``: The PPC and $q$-$u$ plane plots to see the data scatter depending on the algorithms (Appendix of Bach+23b).
* ``figs-mcmc``: The final PPC and MC (Monte Carlo) simulation corner plots (Bach+23b Appendix C)
* ``figs-time``: The time-variation of the polarization degree (not included in Bach+23b)
* ``<OBJNAME>_<OBSDATE>_<rapmode>.csv``: The aperture radius and q/u-related parameters for multiple algorithms (Appendix of Bach+23b)
* ``df_fin.csv``: Extracted only the final results
* ``df_fit_all.csv``: All the fitted results after MC simulation

In ``codes_n_data/extdata`` directory:
* A dirty collection of external data from other sources, excluding those I have no right to open to the public. I had to remove some columns in some files, including ``all_samples.xlsx``.


In ``codes_n_data/figs`` directory:
* Results from ``figures-part1.ipynb`` (figures used for Bach+23a).