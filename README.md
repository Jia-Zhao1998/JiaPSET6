# Jia Zhao PSET6 Reproducible, shareable code

## Overview

The repo contains the code and data to reproduce one figure for the group project of 20.440 Analysis of Biological Network (MIT)

The goal is to use computational methods to unveil cell-cell communication between tissue resident macrophages and other cell types to decode complex cellular circuits and infer novel functions of tissue resident macrophages. 

## Citation/Method

**NicheNet**: a computational algorithm to model intercellular communication

> install.packages("devtools")
> 
> devtools::install_github("saeyslab/nichenetr")

Git repo of NicheNet: https://github.com/saeyslab/nichenetr/tree/master

Browaeys, R.; Saelens, W.; Saeys, Y. NicheNet: Modeling Intercellular Communication by Linking Ligands to Target Genes. Nat. Methods 2020, 17 (2), 159–162. https://doi.org/10.1038/s41592-019-0667-5.

## Data

At a high level, how was the data generated?

**RNA-seq data of fat tissue resident macrophages in fat (VAMs) and other resident cells** 

Moura Silva Hernandez; Kitoko Jamil Zola; Queiroz Camila Pereira; Kroehling Lina; Matheis Fanny; Yang Katharine Lu; Reis Bernardo S.; Ren-Fielding Christine; Littman Dan R.; Bozza Marcelo Torres; Mucida Daniel; Lafaille Juan J. C-MAF–Dependent Perivascular Macrophages Regulate Diet-Induced Metabolic Syndrome. Sci. Immunol. 2021, 6 (64), eabg7506. https://doi.org/10.1126/sciimmunol.abg7506.![image](https://github.com/Jia-Zhao1998/JiaPSET6/assets/67213486/3a65aea6-b3d7-4e45-9b02-ee70328722ec)

## Folder structure

At a high level, what is in each folder and subfolder?

I have subfolders in this repo

- data: the raw data of bulk RNAseq of mouse white adipose tissue: Silva_WAT_cMAF_vs_WT.csv
- code: source files for producing the figure
- figure: the final figure for PSET6
- raw: Intermediate data files produced by the scripts. These files are not git committed.

## Installation

How do I run your code? What software and package versions do I need to install?

R version 4.3.3

RStudio version: 2023.12.1.402

Packages: 
