# LaminB-ID


## **Introduction**
This project was created to improve the current method of phenotyping Lamin B as a readout of the nuclear\
membrane and nuclear pore complex. The script is free for anyone to download and use,\
provided the accompanying [paper](https://www.tandfonline.com/journals/kncl20) is properly cited. This project contains code to analyze the output from\
the [3D ImageJ suite](https://mcib3d.frama.io/3d-suite-imagej) plugin to quantitatively identify six different phenotypes, two normal (ring and diffuse)\
and four abnormal phenotypes (punctate, incomplete, invagination, and folded) of Lamin B staining.

## **Table of Contents**
+ [Description](https://github.com/tes465/LaminB-ID#description)
+ [Installation](https://github.com/tes465/LaminB-ID#installation)
+ [Usage](https://github.com/tes465/LaminB-ID#usage)
+ [Support](https://github.com/tes465/LaminB-ID#support)
+ [Future Projects](https://github.com/tes465/LaminB-ID#future-projects)
+ [How to Contribute](https://github.com/tes465/LaminB-ID#how-to-contribute)
+ [Acknowledgments](https://github.com/tes465/LaminB-ID#acknowledgements)
+ [License](https://github.com/tes465/LaminB-ID#license)

## **Description**
The 3D ImageJ suite is necessary to download and install in ImageJ before the script from this project\
can be used. The results from the measurements of cells stained with Lamin B needs to bestored in a .csv file\
or a text file with columns separated by tabs and each row containing information from a single cell nucleus.\
At minimum, the '3D Moments,' 'Ellipse Flatness,' and the 'Number of Objects' measurements need to be saved.\
The output from this script creates a new file where each cell is phenotyped and a summary output to the\
terminal with the overall counts of each phenotype and the percent of abnormal staining in the two treatment groups.\
\
The script is designed to be used from a computer's command line (the terminal) to process files containing\
Lamin B staining data. The parameters for identifying the phenotypes are set based on measurements from a\
control group, followed by analysis and identification of a cell's phenotype of both the control and\
experimental group. There is expected to be around 50 cells per treatment group. The script functions only\
if the data from the control and experimental group are stored in separate files. To perform an analysis the\
script needs to be invoked. The file names of the control and experimental group and column separator\
(comma or tab depending on file type) can be given as arguments in the correct order, or the script will\
prompt the user for the two file names and the comma separator. Different replicates should be stored in\
different files, so that a separate prompt/analysis is needed for each replicate.\
\
There are a few limitations of the program.\
The first is that there should be at least thirty cells in the control group so the thresholds for\
identifying the phenotypes of cells are correctly set. It is also assumed that the majority of the cells in\
the control group have a normal Lamin B phenotype. This assumption only becomes problematic if approximately\
80-90% of the cells in the control group are abnormal.\
This case is unlikely occur as the control group should be similar to physiological conditions where the\
large majority of cells have a normal Lamin B staining phenotype. A violation of this assumption would result\
in an inaccurate identification of phenotypes in cells in the control and experimental group.\
Another limitation, as outlined in the paper is that the script cannot reliably differentiate between the\
invagination and folded phenotypes. However, this is only a minor issue, as the overall counts of normal and\
abnormal phenotypes are not affected.\
\
The aim of this script is to simplify the process of phenotyping cell and create a uniform and unbiased process\
of assigning normal or abnormal phenotypes to cell. Further, the script can be used to unify nuclear pore\
complex quantification and phenotyping methods, so that findings from different research groups can be compared.

## **Installation**
Currently the only method to install this script is to go to [LaminB_phenotyping.py](link.ca) and download the file.\
Check back later for instructions to install this package from the command line in a terminal.

## **Usage**
Check back later for more detailed usage instructions.\
How to use with examples\
include options (-help)
+ How to prepare for script usage
    + Install the computer code (can add link to installation section)
    + Download the 3D ImageJ suite plugin (add link)
    + Process 3D images of Lamin B staining. Quantify the staining and save the results in a supported\
      file format (.csv or .txt). Specifically the 
    +

## **Support**
The first place to go to for support is the accompanying [paper](https://www.tandfonline.com/journals/kncl20),\
which includes this project. The methods section of the paper includes how the data was obtained for use in the\
computer script. Support for the 3D ImageJ suite plugin can be found at the [plugin homepage](https://mcib3d.frama.io/3d-suite-imagej) or [here](https://www.otago.ac.nz/omni/otago684695.pdf)\
for a brief description on the different functionalities of the features of the plug-in.\
\
Contact todds360@gmail.com for further support related specifically to this project.


## **Future Projects**
This project enables the identification of Lamin B Phenotypes, but future projects may include\
identifying the phenotypes of other nuclear pore complex proteins. The same pipeline used to create\
this script can be used to optimize the phenotyping of the other proteins.\
\
In a much broader context, this script quantitatively assigns a phenotype based on a structure.\
Therefore, there is a possibility that the distinct qualitative staining phenotypes could be \
assigned a phenotype. This could include cell surface proteins or proteins localized to specific\
organelles or areas of the cell.\
\
\
If interested in developing a new project, reach out for support or to begin a collaboration.


## **How to Contribute**
People interested in contributing to this project can reach out to todds360@gmail.com.\
Alternatively, you can create a new branch, make changes, and submit a pull request detailing the changes.\
For major changes, please open open an issue first to discuss your thoughts on how improve the script.


## **Acknowledgements**
The sole author of this software code is Todd Stang.\
I would like to acknowledge the Levin Lab where the research for this project occured\
and Michael Levin and Hannah Salapa for their support with the research.


## **License**
This work is protected under the [GNU General Public License v3.0](https://github.com/tes465/LaminB-ID/blob/main/LICENSE) license.
