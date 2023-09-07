# covid_multiomics_mar2022

## Introduction

These files are Rmd documents and associated datasets that allow for a reproducible analysis in support of the manuscript. 

## data wrangling 

Extensive data wrangling was required to begin analysis work.  

 "import_metadata.Rmd" : 
  - import raw metadata, filter and mutate, and write out a "masterkey" table that associates samples across data types 
  
 "import_munge_RNAseq.Rmd" : 
  - Read in the raw bcmatrix xls files of scaled, log-normed data, row bind into a large table, write out as one CSV for analysis
  
 "import_munge_proteome.Rmd" : 
  - Read the Olink formatted xlsx data, do name fixes, filter for plasma samples, write out CSV
  
"import_munge_exome.Rmd" : 
  - Loop over TSV variant files, combine into one large data table by cohort, filter using various strategies, do data viz 

## sPLS-DA analysis 

"mixomics_sPLS_DA_predictive_OCT2022.Rmd" : 

 - contains code to use mixomics sPLS-DA and DIABLO models to find correlations between RNA-seq and proteomics data
 - uses the munged datasets from the data wrangling code as inputs 
 - performs both RNA-seq and Proteomic single datatype PLS-DA models with covid severity as the outcome (Y)
 - performs integrated RNA-seq and proteomic two-way sPLS-DA (DIABLO) with covid severity as the outcome (Y)

## exome analysis 

 - Exome analysis is currently performed in the file "import_munge_exome.Rmd".  
