## gfcondition: Annual indices of average groundfish body condition 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18211383.svg)](https://doi.org/10.5281/zenodo.18211383)

This repository contains code used to generate sex and maturity specific indices 
of average body condition and associated density distributions for species 
frequently sampled by Canadian Pacific bottom trawl surveys. Common trends in 
body condition indices were then identified using a Bayesian Dynamic Factor 
Analysis implemented with the bayesdfa R package 
(<https://fate-ewi.github.io/bayesdfa/>) and compared with environmental 
indices available in the PACEA R package (<https://github.com/pbs-assess/pacea>).

These analyses are described in:

> English, P.A., Anderson, S.C., and Forrest, R.E. (2026) Body Condition
> as a Shared Response to Environment in a Commercially Important Demersal
> Fish Assemblage. Fish and Fisheries. <https://doi.org/10.1111/faf.70053>

- This repository is structured as an R package.
- All data retrieval, processing, and analysis scripts are found in the `analysis` 
folder and are numbered in the order that they must be run. 
- Scripts load the R package with `devtools::load_all(".")` where necessary.
- Scripts starting with `00-` are for data preparation and are provided for
reference, but do not need to be run on their own. These files are either
sourced by other files, or contain the original 
data retrieval and processing steps used to generate the data files provided.
- Scripts without numbers (`x-`) are for plotting, supplementary tests, 
or summary statistic, and may need to be run after the main analysis is complete.
- Script `05-dfa.R` can be run repeatedly for each sex and maturity class (e.g., 
`set_group <- "mature males"`) and with and without using condition indices where the 
estimated effects of density-dependence have been removed from the estimated annual 
averages (e.g., `adjusted_for_density <- TRUE`). 
<!-- - Note: The sea surface temperature variable from PACEA was reformatted to match the other
spatial variables using the method in `xx-get-oisst.R` the output from which is provided 
in `data-raw/oisst_month_grid26.rda`.-->
