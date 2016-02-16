

# Exploring and Annotating Variants using Bioconductor
Chela James (Adapted from Francesco Lescai 2012)
Institute of Child Health
University College London
c.james@ucl.ac.uk
February 16, 2016

## Introduction

This tutorial is intended to give you an overview of the workflow commonly employed for data generated by parallel DNA sequencing.  Specifically, we will examine data from data from the coding regions of genome, i.e. the exome.  The initial steps of the process are computationally intensive and require some time to be executed so they will be described. But the final steps – annotation and analysis can be done in R.


## Aligning Sequence Data
The file we receive following sequencing is known as a fastq, it typically consists of millions of lines but each sequence read is encoded by four lines
```
@SEQ_ID
GATTTGGGGTTCAAAGCAGTATCGATCAAATAGTAAATCCATTTGTTCAACTCACAGTTT
+
!''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65
```

The id line is unique for each read and it tells us which machine and lane the read comes from and whether it is the first or second of a pair of reads. The second is the sequence of the read, the third a spacer and the fourth an ascii code for the quality of each base call of the sequence read
