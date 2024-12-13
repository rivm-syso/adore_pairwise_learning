# Improving the ecotoxicological hazard assessment of chemicals by pairwise learning employed on a large set of ecotoxicity test data

## Running the experiment

One needs to first download and extraxt the [ADORE](https://opendata.eawag.ch/dataset/adore) data set in the current folder. 

Then download and compile the [LibFM](https://github.com/srendle/libfm) library. In the code **experiments.ipynb** set the *PATH_LIBFM* variable to the directory that contains the LibFM binaries and , the *PATH_CACHE* variable to a directory that can be used to create temporary files for LibFM. The Python notebook calls the LibFM binary for model fitting and prediction, simply by transforming the data set into an approproate format and constructing the command line arguments. You can also call the library directly, the following example is given in the LibFM manual:
`./libFM -task r -train ml1m-train.libfm -test ml1m-test.libfm -dim ’1,1,8’ -iter 1000 -method mcmc -init_stdev 0.1`

You can then run all of the code blocks in **experiments.ipynb** to reproduce the results in the paper. 

The predictions for all possible (species, chemical, duration) triplets are saved in the file **predictions.csv**. This file is uploaded to [Zenodo](https://doi.org/10.5281/zenodo.14449272).

## Authors
Markus Viljanen (markus.viljanen@rivm.nl)
