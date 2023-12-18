# Dataset overview

The dataset was based on de la Cuesta-Zuluaga et al.’s work ‘Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization’, published in Sci Rep in 2018 [7]. We used the  DADA2 denoising tool based on Callahan et al. 's work ‘DADA2: High-resolution sample inference from Illumina amplicon data’ published in Nature methods in 2016 [22]. Table 1 shows the total sample size and sequencing depth before and after denoising. The data quality prior to denoising can be observed in Figure 1.


Table 1: Total sample size and sequencing depth before and after denoising

The maximum length chosen is 251 nucleotides (nts). There are not >99% samples with the same read length. 98% of the samples have the same read length of 251 nts and about 2% are 250 nts with the minimum length of 248 nts. The reads will be truncated to 248. We chose this length to ensure all reads are the same length since 248 is the minimum read length. Otherwise, the read quality was acceptable at each base which is apparent in the read quality plot. This information is obtained from viewing the Interactive Quality Plot of demux.qzv using the QIIME 2 view.
