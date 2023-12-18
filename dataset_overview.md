# Dataset overview

The dataset was based on de la Cuesta-Zuluaga et al.’s work ‘Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization’, published in Sci Rep in 2018 [1]. We used the  DADA2 denoising tool based on Callahan et al.'s work ‘DADA2: High-resolution sample inference from Illumina amplicon data’ published in Nature methods in 2016 [2]. Table 1 shows the total sample size and sequencing depth before and after denoising. The data quality prior to denoising can be observed in Figure 1.

|                   | Before denoising | After denoising |
|-------------------|------------------|-----------------|
| Total sample size | 441              | 441             |
| Sequencing depth  | 4305 - 117562    | 3684 - 106498   |

_Table 1: Total sample size and sequencing depth before and after denoising_

The maximum length chosen was 251 nucleotides (nts). There are not >99% samples with the same read length. 98% of the samples have the same read length of 251 nts and about 2% are 250 nts with the minimum length of 248 nts. The reads will be truncated to 248. We chose this length to ensure all reads are the same length since 248 is the minimum read length. Otherwise, the read quality was acceptable at each base which is apparent in the read quality plot. This information is obtained from viewing the Interactive Quality Plot of demux.qzv using the QIIME 2 view.

We  primarily focus on the metadata categories of “smoker”, “fiber”, “LDL”, and possibly “city”. We will not use every single sample in our analysis since we will be filtering our data to remove nonbacterial (i.e., mitochondrial and chloroplast) sequences, as well as features with <5 frequency to improve the analysis efficiency with PICRUSt2. As we are looking at the fiber and LDL reading, we will also remove individuals that don’t have a recorded fiber level or LDL reading. There is also the potential that we encounter a confounding variable similar to that in a previous years’ UJEMI+ paper using the same dataset [3]; if this occurs we may limit our dataset to one city as it appears location has a highly significant impact on ß diversity metrics [4].

To determine the rarefaction depth, we imported the table.qzv into QIIME 2 view. By checking all metadata categories, we decided to use 22700 as the rarefaction depth. We reconfirm the rarefaction depth with the alpha-rarefaction.qzv and know that 22700 already reaches the plateau point for all samples. At this point, it retained the most features. This sampling depth retained 8,489,800 (54.66%) features in 374 (84.81%) samples at the specified sampling depth. Figure 2 shows the rarefaction plot where the black line indicates what the sampling depth is. With 374 samples retained, and 441 samples to begin with, 67 samples being discarded.

### Justification of data categorisation

Fiber is dramatically under-consumed within the Westernized diet. The Government of Canada recommends a daily intake within 21-25g/day for women and 30-38g/day for men, but consumption surveys in Western populations indicate actual intake is significantly lower [5]. Using the fiber intake data collected by de la Cuesta-Zuluaga et al. [1] we can categorize each individual as consuming either HIGH (≥21g/day for females, ≥30g/day for males) or LOW (below thresholds) fiber.

Consumption of a Westernized diet is also correlated with a significant increase in blood LDL levels [6]. It is generally agreed upon that a “healthy” level of LDL cholesterol in the blood of adults is <100mg/dL [7]. Based on this metric we can categorize each individual as having HIGH (>100mg/dL) or LOW (≤100mg/dL) blood LDL levels.


# References

1. **De La Cuesta-Zuluaga J, Corrales-Agudelo V, Velásquez-Mejía EP, Carmona JA, Abad JM, Escobar JS**. 2018. Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization. _Sci Rep_ 8.

2. **Callahan BJ, Mcmurdie PJ, Rosen MJ, Han AW, Johnson AJA, Holmes SP.** 2016. DADA2: High-resolution sample inference from Illumina amplicon data. _Nat Methods_ **13**:581–583.
3. **Nasseri AR, Parmar D, Tabesh M, Wang J.** 2023. Individuals with abnormal cardiometabolic statuses are more vulnerable to smoking-induced alterations of the gut microbiome in a Colombian population undergoing Westernization. _UJEMI+_ **9**
4. **Shoaib G, Samadi S, Joo JY, Wang J.** 2023. Exploring non-WEIRD populations gut microbiota: the relative importance of obesity metrics on gut microbiome diversity and composition in Colombian adults. _UJEMI+_ **9**.
5. **Quagliani D, Felt-Gunderson P.** 2017. Closing America’s Fiber Intake Gap. _Am J Lifestyle Med_ **11**:80–85.
6. **Asadi Z, Moghbeli M, Khayyatzadeh SS, Mohammadi Bajgiran M, Ghaffarian Zirak R, Zare-Feyzabadi R, Eidi M, Bonakdar MT, Davari H, Mahmoudi AA, Sheikh Andalibi N, A.Ferns G, Ghazizadeh H, Ghayour-Mobarhan M.** 2020. A Positive Association between a Western Dietary Pattern and High LDL-C among Iranian Population. _Res J Health Sci_ **20**:e00485–e00485.
7. **Ibrahim MA, Asuka E, Jialal I**. 2023. Hypercholesterolemia. In Aboubakr S et al (ed), StatPearls. StatPearls Publishing, Treasure Island, FL.



