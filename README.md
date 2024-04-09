# Jia Zhao PSET6 Reproducible, shareable code

## Overview

The repo contains the code and data to reproduce one figure for the group project of 20.440 Analysis of Biological Network (MIT)

Tissue resident macrophages (TRMs) are present ubiquitously in every tissue and organ, yet how they support tissue and organ function is largely unknown. Since intercellular commnunication is critical for tissue homeostasis, the goal is to use computational methods to unveil cell-cell communication between fat tissue resident macrophages, called vasculature associated macrophages (VAMs), and other cell types to decode complex cellular circuits and infer novel functions of tissue resident macrophages. 

## Citation/Method

**NicheNet**: a computational algorithm to model intercellular communication

> install.packages("devtools")
> 
> devtools::install_github("saeyslab/nichenetr")

Git repo of NicheNet: https://github.com/saeyslab/nichenetr/tree/master

Browaeys, R.; Saelens, W.; Saeys, Y. NicheNet: Modeling Intercellular Communication by Linking Ligands to Target Genes. Nat. Methods 2020, 17 (2), 159–162. https://doi.org/10.1038/s41592-019-0667-5.

DESeq2: find differentially expressed genes and plot

Love, M.I., Huber, W., Anders, S. Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2 Genome Biology 15(12):550 (2014)

## Data


**RNA-seq data of VAMs and other resident cells: Silva_WAT_cMAF_vs_WT.csv** 

Moura Silva Hernandez; Kitoko Jamil Zola; Queiroz Camila Pereira; Kroehling Lina; Matheis Fanny; Yang Katharine Lu; Reis Bernardo S.; Ren-Fielding Christine; Littman Dan R.; Bozza Marcelo Torres; Mucida Daniel; Lafaille Juan J. C-MAF–Dependent Perivascular Macrophages Regulate Diet-Induced Metabolic Syndrome. Sci. Immunol. 2021, 6 (64), eabg7506. https://doi.org/10.1126/sciimmunol.abg7506.![image](https://github.com/Jia-Zhao1998/JiaPSET6/assets/67213486/3a65aea6-b3d7-4e45-9b02-ee70328722ec)

## PSET6 Case study

For PSET6, the practice is focused on the infering intercellular communication between VAMs and the primary cell type - adipocytes in white adipose tissue, and here is the essential steps: 

### Workflow: PSET6 covers step 1 and 2


1. Define a sender cell population and a receiver cell population and determine which genes are expressed in both populations:

   Sender: VAMs, receiver: adipocytes

3. (Critical step) Define a gene set. Define differential expressed genes (DEGs) in receiver cells potentially affected by ligands (Most challenging)

   DEGs: Use adipocytes RNA-seq data vs preadipocytes (called FRCs (fibroblast reticular cells) in Moura Silva dataset)

5. Define a ligand set: from sender cells and can potentially bind to receiver cells

6. NicheNet ligand activity analysis: rank ligands based on the gene expression of target genes in the receiver cells

7. Infer top-predicted target genes based on top-ranked ligands


## Folder structure


I have subfolders in this repo

- data: the raw data of bulk RNAseq of mouse white adipose tissue: **RNA-seq > Silva_WAT_cMAF_vs_WT.csv**
- code: source files for producing the figures: **NicheNet_VAMs_PSET6.Rmd**
- figure: the final figures for PSET6:

1. MA_Plot_WT_Adipocyte_vs_FRC.pdf: rough draft 1 of MA plot to visualize the log fold change of gene expression change (M) against the mean of normalized counts of the gene (A) across all samples. In this case, adipocytes and fibroblast reticular cells (FRCs), which are mainly proadipocytes.
2. (perfer to use this for grading purpose) MA_Plot_WT_Adipocyte_vs_FRC-2.pdf: better version of MA plot. ![Link to this MA-plot](https://github.com/Jia-Zhao1998/JiaPSET6/blob/main/figure/MA_Plot_WT_Adipocyte_vs_FRC-2.pdf)
4. Volcano_Plot_WT_Adipocyte_vs_FRC.pdf: Visualize significantly upregulated or downregulated genes in adipocytes vs FRCs 
5. Heatmap_Plot_WT_Adipocyte_vs_FRC.pdf: to show top 5 upregulated genes in adipocytes in the heatmap

- raw: Intermediate data files produced by the scripts. These files are not git committed.

## Installation

R version 4.3.3

RStudio version: 2023.12.1.402

Packages: I included those relevant codes in **code/NicheNet_VAMs_PSET6.Rmd**

> install.packages("devtools")
> 
> devtools::install_github("saeyslab/nichenetr")
> 
> install.packages("tidyverse")
> 
> install.packages("DESeq2")
> 
> install.packages("EnhancedVolcano")
