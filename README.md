# XArray 101 🌍
A quick tutorial into data processing with Python (covers the very basics, but is intended to lead you to utilize [xarray](http://xarray.pydata.org/en/stable/) and the [PyData stack](https://pydata.org)). 

> :warning: **As with most things Python this repository stands on the shoulder of giants!** I used, modified and incorporated quite a few tutorial notebooks from various sources (mostly from the original package authors)! In order to streamline the tutorial I include them instead of merely linking them but credits are given in the various notebooks of this repo.   

## Getting started
If you don't have a Python environment on your machine yet, read the [getting started guide](./GETTING_STARTED.md) and install one with with [Miniconda](https://docs.conda.io/en/latest/miniconda.html). Note that we need a modern python (>= 3.6) - I'd suggest 3.8.

## Notebooks

### Introduction
Notebooks that get you started with the JupyterLab environment, some basic Python intro (mainly intended for people coming from R), and an introduction to some core libraries from the PyData eocsystem that we will use in this tutorial.

#### Jupyter and Python Basics
* Basic intro
* Numpy
* Matplotlib
* Pandas

#### Xarray Intro
* A first intro to XArray

### More stuff
More advanced notebooks also showing how to work with remote sensing data in Python 
and other tools (i.e. the PyViz toolbox or Intake catalogs).

#### Xarray Advanced
Slicing and dicing...

#### Vector Data
Ditch your ArcGIS and just use python (well, geopandas)

#### Remote Sensing
Reading geotiffs and doing some remote sensing with xarray, rasterio and geopandas

#### Visualization
An intro into the Holoviz/ PyViz ecosystem



## Getting started before each session 🏁
In order to be up to date do the following before each session.  

1. Open your terminal app
2. Change into this directory (this should be called `xarray-101` if you did not change it after cloning the repository)
3. Do a `git pull` to update your local files with the latests from the repository (`git pull` is equivalent to a `git fetch`, followed by a `git merge`). If you get notified about conflicts I'd advice you to rename you notebooks that have a conflict with the server version (or delete them if you do not want to preserve the changes) and pull the sever state a second time.  
A more elegant procedure is to:  
    - download the latest from remote without trying to merge or rebase anything: `git fetch --all`
    - save your current state in a branch: `git checkout -b backup-main`
    - reset the master branch to what you just fetched: `git reset --hard origin/main`
4. Activate our conda environment: `conda activate xarray-101`
5. In case the `environment.yml` file was updated we want to update the installed packages in our environment. You can do this with this command: `conda env update --file environment.yml` 
6. Start JupyterLab: `jupyter lab`
