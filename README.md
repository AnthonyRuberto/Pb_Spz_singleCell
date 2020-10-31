# Workflow for manuscript titled **Single-cell RNA sequencing reveals developmental heterogeneity among *Plasmodium berghei* sporozoites**
#### Anthony A. Ruberto1, Caitlin Bourke2, Nicolas Merienne1, Thomas Obadia1, Rogerio Amino1, Ivo Mueller1,2
#### 1 Department of Parasites and Insect Vectors, Institut Pasteur, Paris, France
#### 2 Division of Population Health and Immunity, Walter and Eliza Hall Institute of Medical Research, Parkville, Victoria, Australia


## Contents

R Markdown files containing codes used to analyze *Plasmodium berghei* sporozoites.

To perform the analysis in its entirety, download and unzip "STARsoloOutputs".

Once complete you will find 3 folders that corresponding to the each of the *Plasmodium berghei* 10X scRNA-seq runs.

Modify the path of these folders in the Rb_Spz_10X.Rmd so that they can be read to R.

When saving the RDS files be sure you have the correct output path specified.

## Markdown file descriptions

Rb_Spz_10X.Rmd allows you to upload and modify the matrices individually (i.e remove empty droplets, remove cells with high gene counts, filter low expressing 
genes, add metadata). These objects are also used for the integration portion of the study relevant to Figure 3.

Pb_Spz_10X_2.Rmd describes the workflow used to integrate the three 10X scRNA-seq datasets from Pb sporozoites. It generates 2_PbInt_LogNorm_CCA.rds which contains the Seurat object used for the analyses in Figures 1 and 2.

Pb_Spz_10X_3.Rmd describes the workflow used to cluster the integrated 10X scRNA-seq data and generates 3_PbInt_LogNorm_Clustered.rds. Workflow used to perform analyses related to Figure 2.

Pb_Spz_10X_4.Rmd describes the workflow used to upload and process the MCA data. It requires the SS2_pheno.txt and SS2_counts.txt (accessible in this repository or from [1]) as inputs and generates 4_MCA_SS2_seurat.rds which is the data in Seurat format containing only the parasite life-stages in the mosquito (+ ejected sporozoites). 

Pb_Spz_10X_5.Rmd described the workflow used to integrate the MCA (Smart-Seq2 scRNA-seq data) with the 10X scRNA-seq data generated in this study. It requires the 
1_Pb1_sce.rds, 1_Pb2_sce.rds, 1_Pb3_sce.rds, and 4_MCA_SS2_seurat.rds files as inputs and generates two files: 
5_Pb_integrated_MCA_10X.rds and 5_Pb_integrated_10X_only.rds. These files are related to the outputs shown in Figures 3 and 5.

Pb_Spz_10X_6.Rmd described the workflow used for the trajectory analysis and generates the SCE object 6_Pb_integrated_10X_only_pseudotime.rds. This file is related to Figure 4.

## Outputs

In the event you do not want to perform the analysis, the .rds files from each step can be downloaded from Zenodo available upon publication.

## Links

[1] https://github.com/vhowick/MalariaCellAtlas/tree/master/Expression_Matrices/Smartseq2






