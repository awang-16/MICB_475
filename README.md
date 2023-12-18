# MICB475 Project 2 Lab notebook
This repository contains ongoing notes on project 2, compiled by AW, IP, SD, SA, and TW. The project aims to elucidate the combined impacts of diet Westernisation (low fibre consumption and high blood LDL levels) and smoking on gut microbial metabolism.

The file MICB475_R_code.Rmd should be run to reproduce all figures seen in the manuscript. It loads data produced by QIIME2 and PICRUSt2 processing, the bash scripts for which are also displayed here.

### R code outline

**Alpha diversity** (line 54): performs alpha-diversity analyses (Observed, Shannon, Chao1, ACE, Simpson, InvSimpson, and Fisher) on the data as categorised both by smoking and LDL status, and by smoking and fiber status. Produces box plots and statistical test results (One-Way ANOVA).

**Beta diversity** (line 173): performs beta-diversity analyses (weighted and unweighted unifrac, Bray-Curtis, and Jaccard) using the phyloseq package on the data as categorised above. Produces PCA plots, performs statistical tests (PERMANOVA).

**DESeq2 analysis** (line 251): uses DESEq2 package to perform differential abundance analysis, producing volcano and bar plots to show differentially abundant ASVs labelled at the genera level.

**PICRUSt2 analysis** (line 348): uses ggpicrust2 package to analyse pathway patterns and changes in microbiota function, producing bar plots annotated with function.


### Papers referenced

[Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization](https://www.nature.com/articles/s41598-018-29687-x) Scientific Reports, Sept 2018.

* Original dataset compiled by de la Cuesta-Zuluaga et al of Columbian adults' fecal microbiomes.

[Exploring  non-WEIRD  populations  gut  microbiota:  the relative  importance  of  obesity  metrics  on  gut  microbiome diversity and composition in Colombian adults](https://ojs.library.ubc.ca/index.php/UJEMI/article/view/198186/192791?fbclid=IwAR0iTZopMvDnj4u4ff_Y713ByjeSGnvi86pGAkuLxliEXvQDzXDXm4_k-OA) UJEMI+ Volume 9, Sept. 2021. 

* Significance analysis of all metadata categories on alpha- and beta-diversity metrics; high-significance factors include city, sex, medication, fibre intake etc.

[Individuals with abnormal cardiometabolic statuses are more vulnerable  to  smoking-induced  alterations  of  the  gut microbiome  in  a Colombian  population  undergoing Westernization](https://ojs.library.ubc.ca/index.php/UJEMI/article/view/198169/192803) UJEMI+ Volume 9, Sept. 2021

* Investigates relationship between cardiometabolic status and smoking on gut microbiome, has supplementary figure indicating involvement of a confounding variable causing differences in population unrelated to smoking status.

