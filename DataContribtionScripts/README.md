# Instructions to contribute publicly available data under DOI

Currently we assume that the data is in [Zenodo](www.zenodo.org), but this
should work also for other sources (not tested).

1. Collect the information for the first cell of the [Jyputer notebook (AddData.ipynb)](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs/blob/master/DataContribtionScripts/AddData.ipynb).
The required information is marked with bold here:

>DOI="**Give the DOI here**" \
>def_file  = "**Give path to the definition file used to calculate order parameters. Format and examples are [here](https://github.com/NMRLipids/MATCH/tree/master/scripts/orderParm_defs)**" \
> \
>user_information = """ \
>**Give free text information about your system, e.g., POPC lipid bilayer** \
> \
>#NMRLIPIDS BEGIN \
>@SIM \
>@SOFTWARE=**Give the name of used simulation program here, e.g., gromacs, namd, etc.** \
>@FF=**Give the name of the force field, e.g., CHARMM36** \
>@FF_SOURCE=**Give the source of the force field, e.g., CHARMM-GUI** \
>@FF_DATE=**Give the date of the force field, e.g., when downloaded from CHARMM-GUI** \
>@TRJ=**Give the name of the trajectory in the Zenodo repository, e.g., trr or xtc file in Gromacs** \
>@TPR=**Give the name of the structure file in the Zenodo repository, e.g., tpr in Gromacs** \
> \
>#NMRLIPIDS END

Example can be found from [here](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs/blob/master/DataContribtionScripts/exampleDATAnamdPOPC.txt). 
Note that if you have several trajectories under the same DOI, you can put them in the same file 
as shown in [this example](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs/blob/master/DataContribtionScripts/exampleDATAmultipleTRAJS.txt).

2. Deliver this information to us, for example, by commenting [the blog]().
If you want to analyze the data yourself go to step 3.

## Running analysis for the data

3. Fork this [GitHub repository](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs) to your own GitHub account and local computer.
4. Copy the information collected in step 1 into the first shell of
the [Jyputer notebook](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs/blob/master/DataContribtionScripts/AddData.ipynb),
and define working directory at your local computer in the second cell.
5. Run the Jupyter notebook to calculate the order parameters. 
Results will be written in the [Data/Simulations/**DOI**.X](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs/tree/master/Data/Simulations)
folder, where X refers to the number of simulation in the DOI.
6. Commit the files *OrderParametersX.dat* in the *Data/Simulations/**DOI**.X* directory to your fork
and make a pull request to the [master branch in the NMRlipids project](https://github.com/NMRLipids/NMRlipidsVIpolarizableFFs).
**Do not commit the trajectories to git. This will cause problems because git cannot handle large files.**
