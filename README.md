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
To download this computer code, click on the releases tab to the right and download the compressed files.\
The LaminB_Phenotyping.py file contains the computer script and is the file that will be used in the next steps.

## **Usage**
1. How to prepare files for script usage
    + Install the computer code (see previous section)
    + Download the [3D ImageJ suite plugin](https://mcib3d.frama.io/3d-suite-imagej)
    + Process 3D images of Lamin B staining. Quantify the staining and save the results in a supported\
      file format (.csv or .txt). Columns should be separated by commas (.csv file) or tabs (.txt file)
    + The first column should be contain headers (the title of the columns) worded exactly as from the\
      the ImageJ 3D plugin 3D measurements. The column names are hard written into the code and if worded\
      slightly different will result in errors. This is a common area to check if the script does not work\
      as expected
    + At minimum, the '3D Moments,' 'Ellipse Flatness,' and the 'Number of Objects' measurements need to be saved.
2. How to prepare the computer for script usage
    + Make sure that python is downloaded and able to be used at the command line
    + `$ python --version` will return the version of python downloaded on the computer
    + If this command returns an error, python will needed to be downloaded for [mac](https://www.python.org/downloads/macos/) or [windows](https://www.python.org/downloads/windows/)
    + After downloading the file permission to run the script must be given, this is accomplished by the\
      command `$ chmod 764 LaminB_Phenotyping.py`
3. How to invoke/use the script
    + At the computer's command line use `$ ./LaminB_Phenotyping.py [OPTIONS]`
    + The only current option is -help for a short description to use the code
    + There is a choice to use the code with three arguements or with none. If no arguments are used, the\
      code will prompt the user for the first file name to establish the thresholds for phenotyping. (this\
      should be the control treatment, the next prompt is to enter the delimiter of the file (a comma, space\
      or tab). The final prompt is for the second file name, which is expected to be the experimental treatment\
      file.
    + The code can also be used to with the files and delimiter given as arguements when invoking the code.
        + The first argument is the file to establish the measurement thresholds (likely the control file)
        + The second arguement is the delimiter of the file (comma, space or tab)
        + The third argument is the second file to phenotype, likely the experimental treatment data
    + In order for the script to access the files, the current directory must contain the two files and the python file.
        + The first option is to save the files in the root(Home) directory
        + The second option is to change the current directory to the directory where the files are saved.\
          This is done by used the cd command. For example, on a Mac if the files are saved in the documents\
          folder use `$ cd Documents/` to change the current directory to Documents. Once the current directory\
          contains the two files, the script can be used properly.
4. Examples
    + Without arguments:
      ```
      $ ./LaminB_Phenotyping.py 
      Please enter the full name of the file to open including the format (.csv or .txt): controldata.csv
      Please enter the delimiter of the file (tab key, space key, or ','): ,
      Control group totals: 
      Ring, count: x
      Diffuse, count: x
      Punctate, count: x
      Incomplete, count: x
      Invagination, count: x
      Folded, count: x
      The percent of cells with abnormal staining is: x.xx
      
      Please enter the full name of the siRNA treatment file to open including the format (.csv or .txt): treatmentdata.csv
      Treatment group totals: 
      Ring, count: x
      Diffuse, count: x
      Punctate, count: x
      Incomplete, count: x
      Invagination, count: x
      Folded, count: x
      The percent of cells with abnormal staining is: x.xx
      ```
    + With three arguments
      ```
      $ ./LaminB_Phenotyping.py controldata.csv , treatmentdata.csv
      Control group totals:
      Ring, count: x
      Diffuse, count: x
      Punctate, count: x
      Incomplete, count: x
      Invagination, count: x
      Folded, count: x
      The percent of cells with abnormal staining is: x.xx
      
      Treatment group totals:
      Ring, count: x
      Diffuse, count: x
      Punctate, count: x
      Incomplete, count: x
      Invagination, count: x
      Folded, count: x
      The percent of cells with abnormal staining is: x.xx
      ```
5. Important Points
    + Any combination of 0, 1, 2, or 3 arguments can be used when invoking the command.\
      The order of the arguements must always be control file, delimiter, experimental file\
      and any arguments not given will be prompted.\
      For example if only 1 argument is given, the user will not be prompted for the first file name,\
      but will be prompted for the delimiter and the second file.
    + Entering file names when prompted need to entered exactly as written including spaces and capitalization
    + If entering the file names as arguements spaces needed an escape character before the space
      For example the file 'control data.csv' has to be written as `control\ data.csv`
      The tab key can be used to autofill parts or all of the file name depending if other files\
      contain the characters after the tab key is used.
      
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
