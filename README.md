# Uncertainty in Thermosensory Expectations Enhances an Illusion of Pain
Public repository for data, code and figures used in this study

## Table of Contents
1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Directory Structure](#directory-structure)
4. [Access](#access)
5. [Reproducibility](#reproducibility)
6. [Usage](#usage)

## Abstract
The human brain has a remarkable ability to learn and update its beliefs about the world. Here, we investigate how thermosensory learning shapes our subjective experience of temperature and the misperception of pain in response to harmless thermal stimuli. Through computational modeling, we demonstrate that the brain uses a probabilistic scheme to update beliefs about temperature changes based on their uncertainty. We find that these expectations directly modulate the perception of pain in the thermal grill illusion. Quantitative microstructural brain imaging revealed that the myeloarchitecture and iron content of the somatosensory cortex, the posterior insula and the amygdala reflect inter-individual variability in computational parameters related to learning and the degree to which uncertainty modulates illusory pain perception. Our findings offer a new framework to explain how the brain infers pain from innocuous thermal inputs. Our model has important implications for understanding the etiology of thermosensory symptoms in chronic pain conditions.

## Introduction
This repository contains all the scripts necessary to execute and generate the results, analyses, and the manuscript for the research paper titled "Thermosensory Expectations Modulate Illusory Pain via Bayesian Predictive Coding." To ensure complete reproducibility, the project is integrated with the Open Science Framework [OSF](https://osf.io/pw956/)  to facilitate either the rerunning of analyses or the retrieval of results. Additionally, the computational environment required for these analyses can be precisely replicated using the [renv](https://rstudio.github.io/renv/articles/renv.html) package, which is specifically designed for managing R environments. This setup guarantees that other researchers can accurately reproduce and build upon the work presented in this study.


## Directory Structure

The repository is structured in the following way:

```         
Thermal Pain Learning/
├── README.md             # Overview of the project.
│
├── Figures/              # Figures generated from code to the from the final manuscript.
│   └── ... 
│
├── Manuscripts/          # Folder containing everything needed to recreate the final manuscript in pdf,docx and html.
│   ├── Manuscript.Rmd                # Rmarkdown for the final manuscript.
│   ├── Supplementary material.Rmd    # Rmarkdown for the supplementary material of the final manuscript.
│   └── Kntting files/                # Files used for knitting the manuscript.
│
├── Markdowns/            # Folder containing markdowns for running the analyses and plots.
│   ├── Analysis.Rmd                  # Rmarkdown for for running the main analyses in the manuscript.
│   ├── Supplementary Analysis.Rmd    # Rmarkdown for the supplementary analyses in the manuscript.
│   ├── plots.Rmd                     # Rmarkdown for the plots used in the manuscript.
│   └── Control analyses.Rmd          # Rmarkdown for the control analyses done.
│
│
├── Pictures/             # External pictures used to produce the final figures for the manuscript.
│   └── ... 
│ 
│ 
├── Matlab/               # Folder containing MATLAB scripts plots and data from both the computational modeling and VBQ analyses.
│   ├── Matlab data                  # Folder containing all the raw data stored from the experimental script.
│   │    └── ... 
│   ├── pain_main.m                  # Main MATLAB script for running all the computational analyses.
│   ├── painLearning_ver4            # Folder containing MATLAB scripts for running the experiment with instructions.
│   │   └── ... 
│   ├── scripts                      # Folder containing MATLAB written scripts used in the Main MATLAB script.
│   │   └── ... 
│   └── VBQ                          # Folder containing files and script to run the VBQ brain analysis.
│
├── renv/                 # Directory for the R enviroment
│   └── ... 
│
├── scripts/              # Directory containing all R scripts in the project
│   ├── utils.R                       # Utility functions to gather data, extract summary statistics etc.
│   ├── plots.R                       # Functions used to produced the figures in the final manuscript.
│   └── supplementary_functions.R     # Functions to run the supplementary analysis, produce plots, tables etc.
│
├── renv.lock             # File used to download and install all necessary packages in the versions used to generate the manuscript.
│
└── run.sh                # Bash file to knit the Manuscript for all three document types.


```

## Access

To get access to the data for running the analysis a OSF-token is needed, as the data is stored in the following [OSF-project](https://osf.io/pw956/). It is recommended to make an osf folder that contains an osf.txt file which on the first line contains the OSF-token, however make sure that this token is not shared or pushed to github. In the current gitignore an osf folder will be ignored.
To get access to the repository users are recommended to clone the respository with the following command in the terminal

```bash
git clone  https://github.com/Body-Pain-Perception-Lab/Pain-Thermal-Learning.git
```

## Reproducibility

To enhance reproducibility this project is setup with R-package "renv"", ensuring the same packages and versions of these are loaded. This means that users should install the "renv" package and after cloning the repository, run the following code in the console (Not terminal).

```r
renv::restore()
```

This will download and install all the needed packages to run the analysis from scratch with the same version of packages used to generate the manuscript. 


## Usage

You can use this repository in various ways. Choose the one that suits your needs: Note you have to complete the [Access](#access) step to get get the data from OSF. 

1. **Method 1 - Re-create manuscript without rerunning analysis**:
   -  Go to the terminal and write ```bash bash run.sh```, which will rewrite the Manuscript in all 3 document types.
   -  Open the Manuscript folder and knit the [Manuscript.Rmd](./Manuscripts/Manuscript.Rmd) file to the desired format (.docx, .pdf or .html). 

2. **Method 2 - Running the main analysis line by line**:
   - Open the Markdown folder and go through the [Analysis.Rmd](./Markdowns/Analysis.Rmd) markdown.

3. **Method 3 - Rerunning the plots line by line**:
   - Open the Markdown folder and go through the [Plots.Rmd](./Markdowns/Plots.Rmd) markdown.
   - To view the plotting functions users are encouraged to check out the [plot.R](./scripts/plots.R) script inside the scripts folder.


