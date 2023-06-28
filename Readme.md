# Hello! Welcome to my repository for Gordon et. al 2023 (submitted to ERL fingers crossed)

This repository contains all the code to repeat the analysis in the paper but has some requirements:

### Environment
All code is written in Python 3.9. On top of the basic packages (numpy, matplotlib, scipy), this project uses 
* [tensorflow 2](https://www.tensorflow.org/install) for creating the ANNs.
* [scikit-learn](https://scikit-learn.org/stable/install.html) for K-means clustering
* [xarray](https://docs.xarray.dev/en/stable/getting-started-guide/installing.html) for preprocessing data
* [cartopy](https://scitools.org.uk/cartopy/docs/latest/installing.html) to make map data
* [cmasher](https://cmasher.readthedocs.io/user/introduction.html#how-to-install) because I like these colorbars

### Data
This project uses sea surface temperature output from the CESM2-LE which can be accessed through the [Climate Data Gateway at NCAR](https://www.earthsystemgrid.org/dataset/ucar.cgd.cesm2le.atm.proc.monthly_ave.SST.html). This data has also been regridded to 5x5 prior to the project. LMK for help with this

### A fun-loving attitude
I feel like this one is self-explanatory

## Repo Contents
I would recommend running the files in the following order to recreate the project (but you do you I guess)

1. calculateSSTanoms.py takes the individual ensemble member files and calculates annual means. These are saved to files such that each file contains all ensemble members (variants) for model years 1850-2100.
2. train_optimalmodel.py is where we train the ANNs. This pulls from files in the functions/ directory preprocessing.py metrics.py ANN.py and experiment_settings.py and saves the individual ANNs to a models/ directory. This latter directory is not included in the.
3. load_valmetrics.py loads in all the trained models 

