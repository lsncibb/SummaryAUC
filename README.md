# SummaryAUC






### Input

prs.model.file, a three columns txt file, "rsID", "Effective_Allele" and "BETA", no header is needed.

gwas.summary.stats.file, GWAS summary statistics file, with "CHR", "SNP", "A1"(Effective Allele), "MAF", "BETA" or "OR", "P" and "INFO"(optional), header is required.

N0, Number of Controls.

N1, Number of Cases.

soFile, "getAdjCorrelation.so", which can be compiled through "R CMD SHLIB getAdjCorrelation.c" in the command line 

KG.plink.pre, 1000 genome plink format file pre. The 1000 genome plink files can be downloaded ![here](https://www.dropbox.com/sh/d5y35kd9by72ejx/AAA0I2DfFy4kDeE-sEM4dCBQa?dl=0)

pos_thr, the threshold for distance of SNPs, correlation will be caculated for any SNP pairs within this distance 

flag.correlation.adj.imputated.data, a logical flag, If FALSE, 1000 genome plink data will be used for correlation adjust. If TRUE, imputation data will be used for correlation adjust, here, imputation should be run with the genotyped SNPs only on impute2, and the imputation results should be split into 22 chromosomes in to such format: first five columns must be "CHR", "SNP", "POS", "A1" and "A2", the rest columns are samples' dosage for "A1", each column for a sample (file name should be "dosage.chr.ChromsomeNumber.txt.gz",  ChromsomeNumber is 1, 2, 3...22, no header is needed).

### Usage:
The current version only work on Unix, Linux and Mac System, R(>=3.4.4), R package "mvtnorm" and GCC(>=4.4.7) are required.

Modify the parameters in the auc.R, and run 

Rscript auc.R



## Example



![Display Figure](https://github.com/lsncibb/AUC_GWAS/blob/master/demo.png)

## Future extensions


## Reference
Lei Song, Aiyi Liu, Molecular Genetics of Schizophrenia Consortium, Jianxin Shi. SummaryAUC: a tool for evaluating the performance of polygenic risk prediction models in validation datasets with only summary level statistics. 

## Contact
* Lei Song, lei.song@nih.gov
* Jianxin Shi, Jianxin.Shi@nih.gov

