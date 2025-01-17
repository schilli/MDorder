# MOP*S*<sup>2</sup> &mdash; Molecular Order Parameters *S*<sup>2</sup>

<!-- Logo from https://pixabay.com/p-827711 ; License: CC0 Public Domain, Free for commercial use, No attribution required -->
<a href="https://github.com/schilli/MOPS">
    <img src="https://github.com/schilli/MOPS/blob/master/mops_small.png" alt="MOPS logo" title="MOPS" align="right" width=40% />
</a> 
 
Version: 1.0

<!-- MOP*S*<sup>2</sup> &mdash; Molecular Order Parameters *S*<sup>2</sup> -->

Compute bond vector *S*<sup>2</sup> order parameters from MD trajectories.

> Ein Leben ohne Mops ist möglich, aber sinnlos. &mdash; *Loriot*  

> A live without tug is possible, yet meaningless. &mdash; *Loriot*  

A publication describing the methods used in this program in detail is under way.



# How to Install
MOP*S*<sup>2</sup> is compatible with python 2 and 3 and runs on Linux, maybe on MacOS as well (untested).  

## Install with Anaconda (Recommended)
This method is recommended, as it leaves the system environment and Python untouched.

1. Download and install the [Anaconda python distribution](https://www.continuum.io/downloads "Continuum Analytics Anaconda download")
2. Create a new environment with the [MDTraj package](https://github.com/mdtraj/mdtraj "MDTraj") installed:  
`conda create --name MOPS mdtraj matplotlib ipython`
3. Activate environment:  
`source activate MOPS`
4. Download and install MOP*S*<sup>2</sup>:  
`git clone https://github.com/schilli/MOPS.git`  
`cd MOPS`  
`python setup.py intall`
5. To update to a newer version go to the MOP*S*<sup>2</sup> directory cloned with git and pull the changes:  
`git pull`  
6. Install again:  
`python setup.py install`

## Install with System Python
1. Install git and Ipython with your systems package manager
2. Install mdtraj and matplotlib with pip:  
`pip install mdtraj matplotlib`
2. Download and install MOP*S*<sup>2</sup>:  
`git clone https://github.com/schilli/MOPS.git`  
`cd MOPS`  
`python setup.py intall` 
3. To update to a newer version go to the MOP*S*<sup>2</sup> directory cloned with git and pull the changes:  
`git pull`  
4. Install again:  
`python setup.py install`
 

# Usage

## Workflow
As the computation of the bond vector correlation functions and the computation of order parameters from the correlation functions can both take some time,
their computations have been split into separate steps in the workflow.
That means:
1. Compute correlation functions.
2. Estimate S2 order parameters from the correlation functions with one of the available methods.

You should provide trajectory data that contains only protein atoms, without solvent.
It might work with solvent, but the trajectory will much load slower.

## Standalone Executable

The module automatically installs an executable `MOPS` in the users `$PATH` that will print detailed usage instructions when called with the `-h` flag.

## From a Python Script
After installation, there will be several files for testing and documentation of the API in your `$PATH`.
These can also be found in the `MOPS/demo` subdirectory.
The `which` command will help you to locate them.
They are well documented and demonstrate how to use the API of MOP*S*<sup>2</sup> from the command line and in your own Python scripts.
In addition, each function and class comes with a docstring describing its usage and the meaning of arguments and return values.
It is a good idea to import the MOPS module in an interactive Ipython session and to read the docstrings with the `?` operator, e.g.:  
```python
In[1]: import MOPS as mops
In[2]: mops.OrderParameter?
```

The API documentation scritps available are:
* `demo_corr_fit.py`: Computes the internal correlation functions with prior removal of the global rotation of the protein by superposition of backbone atoms.
* `demo_corr_nofit.py`: Computes the correlation functions without removal of the global rotation of the protein.
* `demo_AIC.py`: Computes order parameters with the general Lipari-Szabo model and selects the best model (i.e., number of exponentials fitted) based on the Aikaike Information Criterion (AIC).
* `demo_direct.py` : Computes order parameters with the direct method described in Trbovic et al. Proteins (2008). doi:10.1002/prot.21750
* `demo_mean.py` : Computes order parameters as the mean of the internal bond vector correlation function convergence value


# Author
Oliver Schillinger

## Contact via
Prof. Dr. Birgit Strodel  
[Computational Chemistry Group](http://www.strodel.info/ "strodel.info")  
[Institute of Complex Systems 6 &mdash; Structural Biochemistry](http://www.fz-juelich.de/ics/ics-6/EN "ICS-6 Webpage")  
[Forschungszentrum Jülich](http://www.fz-juelich.de/portal/EN "FZJ Webpage"), Germany  
 



