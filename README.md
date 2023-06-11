# CGS-Tools
Description of methods to access CGS models results using kaipy

# Introduction
This repository provides basic instructions for setting up and using the kaipy package for accessing results from the MAGE models.  At the moment this software package is in beta as we would appreicate feedback on the tools as well as contributions.  Questions and feedback can be directed to Michael Wiltberger via email to wiltbem@ucar.edu.

# Prerequsites 
The tools for accessin MAGE model data are bulit upon Python so a working knowledge of python is requried to use them.  You will also need an installation of python that allows you to install packages.  While technically not required JupyterLab will also be helpful since we will be providing notebooks that provide examples of ways to plot and access the model results.

# Installing kaipy

We have made kaipy installed via pip from the PyPi index.  We are currently working a more tight integration with conda, but for now pip is the prefered method doing installations.  

First step is to create virtual python environment to use with the installation of the tools.  You may chose any name for the environment we are going to use `cgs-kaipy` for this tutorial. Using the conda p

```
()$ conda create -n cgs-kaipy python=3.8
()$ conda activate cgs-kaipy
(cgs-kaigy)$ pip install kaipy
```

After completing this step you will have a conda virtual environment that has the kaipy packages as well as some scirpts for producing quicklook plots and conducting analysis of MAGE model results.  If you want to use this environment with JupyterLab you need to use ipykernels to make it available to JupyterLab.  Starting by installing `nb_conda_kernels` into your base conda virtual environment.

```
(base)$ conda install -c conda-forge nb_conda_kernels
```

and then we can make the kernel available JupyterLab via 

```
(base)$ conda activate cgs-kaipy
(cgs-kaipy)$ conda install ipykernel
(cgs-kaipy)$ conda deactivate
```
One last thing before we leave the installation step, making note of where python has installed the analysis scripts and notebooks will be helpful a little later on in this tutorial.  The following command will get the location of the directory from the pip command.

```
(cgs-kaipy)$ pip show -f kaipy | grep Location | awk '{print $2}'
```
making note of this directory or storing it in an environment variable will be helpful.  If you are using csh the following command will save it into environment variable

```
(cgs-kaipy)$ setenv CGSKAIPY `pip show -f kaipy | grep Location | awk '{print $2}'
```

# Globus for MAGE data access
Simulation data can get quite large and that is certainly the case with the MAGE model components.  We are using Globus to sharing access to simulation results.  You will need to sign up for a free account at [Globus.org](https://www.globus.org).

Once you login into the website you can use the file manager to search for the "GAMERA Parallel Test" collection and download the files to your local machine for data processing.  The files can also be accessed by [clicking here](https://app.globus.org/file-manager?origin_id=2c3a2a06-19e4-41d0-ba3c-77a59e501a67&path=%2F)

<img width="541" alt="image" src="https://github.com/wiltbemj/CGS-Tools/assets/5824382/6011e370-741c-4a18-bd68-051ec1fd8805">





