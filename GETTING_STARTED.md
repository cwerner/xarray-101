# Getting started guide

This small guide will help you get setup on your machine. 
Depending on the machine you use and the current state you might not need to
do any of the steps or all...

In this course we use the [Anaconda Python Distribution](https://anaconda.org) to simplify getting all required dependencies and a consistent environment for Windows, Linux and Mac users.

## Installing Anaconda

We will use the Miniconda distribution as we will install the required packageds for this course ourselves. You can get it from [here](https://docs.conda.io/en/latest/miniconda.html).

> Miniconda is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others. Use the conda install command to install 720+ additional conda packages from the Anaconda repository.

Downloads: [Windows](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe), [Mac](https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh), [Linux](https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh)

Run the installers on your system and follow the instructions...

We use Anaconda since it not only provides python packages (you could install them using `pip` from [pypi.org](https://pypi.org), too) but also the often required system libraries that are used by these packages. This is not a big issue on Linux or Mac (if you use `homebrew` to install libraries on a Mac), but super helpful on Windows since installing these libraries manually there is a major hassle! 

Once installed you need to initialize conda in your terminal (Windows users should find a new entry in the start menu already).

In the terminal we can now work with anaconda by using the `conda` command.

> You can find a handy cheatsheet for the most important commands [here](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf).

## Setup files for our course

The code and instructions for this course are hosted in [my github account](https://github.com/cwerner/).

In particular, the required repository is called `xarray-101` and is located [here](https://github.com/cwerner/xarray-101.git).

Steps:  
* Install `git` in your environment (if you don't have it yet)
* Clone the repository 
* Use the `environment.yml` file from the repo to create a dedicated conda environment for our course 
* Switch to the environment and start `jupyterlab`

### Use Git to clone our repository

We get our notebooks from [github](https://github.com). Going into details about `git` here is beyond what we can cover, but essentially `git` is the current defacto standard source control system for open-source software. Pretty much all python software projects are hosted there and it's free for public repos for anyone.

To get a repository from github you need to `clone` it to your machine. 

Open a terminal, navidate to a directory where you want to place the file and type this command into the terminal:  

```
git clone https://github.com/cwerner/xarray-101.git
```

You will see the files being pulled down. Once it's finished you should have the directory `xarray-101` in your current position. Change into this directory now.

> :warning: **NOTE**: If you do not have `git` installed in your system you can install it through conda with  
`conda install git`


### Install the packages required for our tutorial

Anaconda comes with a so-called `base` install - a curated list of packages already installed. Miniconda has less of those, but this is what we actuall want since we actually prefer to install them ourselves.

By using `environments` in anaconda we can have many different versions of packages installed and are able to switch back and forth between them. It is good practice to always use a fresh environment for a different project and not "pollute" the `base` environment. You can create a new environment manually using  

`conda create --name my_new_env`

Then you can activate this environment with  

`conda activate my_new_env`  

Another (better) way of achieving is to use an `environement.yml` file that also contains a lisgt of packages that should be installed in this new environment. You find our file in the tutorial directory.

The content looks like this:  
```name: xarray-101
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.8
  - jupyterlab
  - nodejs
  - holoviews
  - geoviews
  - pandas
  - xarray
  - rioxarray
  - datashader
  - intake
  - intake-geopandas
  - intake-xarray
  - matplotlib
  - s3fs
```

You can create the the environemt and install the packages using this file with  
`conda env create -f environment.yml`

Briefly about the files' content:
* the name defines the environments' name (use it to activate it)
* a channel is a collection of packages (by default this is `default`, but newer and a larger selection of packages is contained in `conda-forge`; that's why we put it on top so it takes priority)
* dependencies list all the packages we want to install into our envrionment

> :warning: **Note:** You should be able to see if you have the right environment activated by a change of your terminals' prompt. You should see `(xarray-101)` in the terminal if you have activated our repository sucessfully.

## Install JupyterLab extensions
The JupyterLab GUI can be extended with labextensions. This enables a more rich IDE experience, but unfortuantely these packages depend on `node` and `javascript` so they have to be installed manually (and not automated via the `environment.yml` file).

```
jupyter labextension install @jupyter-widgets/jupyterlab-manager jupyter-leaflet @pyviz/jupyterlab_pyviz
```

## Start the JupyterHub environment

We use JupyterHub for our course. This provides a interactive development environment (IDE) in the browser where we can run our python code.

You can start it form the terminal with:  
`jupyter lab`



