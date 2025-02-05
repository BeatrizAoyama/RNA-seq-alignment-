# RNA-seq alignment

# Link:

Kallisto (https://github.com/pachterlab/kallisto)

# **Script:**

#!/bin/bash

/ngs/programas/miniconda2/bin/kallisto quant -i /ngs/genomas_ref/Rattus_norvegicus/cdna/Rattus_norvegicus.Rnor_6.0.cdna.all.idx -o p2contvsub_alinha_kallisto/ -b 100 --single -l 180 -s 20 p2contv_S41_L006_R1_001.fastq.gz


# **Script explanation:**


***/ngs/programas/miniconda2/bin/kallisto quant:*** Path where the software is located. The software name is *kallisto quant* and it runs the quantification algorithm

**-i /ngs/genomas_ref/Rattus_norvegicus/cdna/Rattus_norvegicus.Rnor_6.0.cdna.all.idx:** The -i option specifies the path to the index file. The rest of the command indicates the location of the reference genome, which in this case is from the organism Rattus norvegicus (Rnor 6.0)

**-o p2contvsub_alinha_kallisto/:** The -o option specifies the output directory where the results will be stored, in this case *p2contvsub_alinha_kallisto/*

**-b 100:** The -b option sets the number of bootstrap samples to 100. Bootstrapping helps to estimate the uncertainty of the abundance estimates
#
**--single:** indicates that the input data consists of single-end reads. But it can changes if your input data consisted of pair-ended reads

*In that case*, the input file should be:

***p2contv_S41_L006_R1_001.fastq.gz:*** for the first end of cDNA fragment sequenced

***p2contv_S41_L006_R2_001.fastq.gz:*** for the second end of cDNA fragment sequenced

# 

**-l 180 -s 20:** The -l option sets the average fragment length to 180 bases, and the -s option sets the standard deviation of the fragment length to 20 bases

**p2contv_S41_L006_R1_001.fastq.gz:** Input .fastq file

# **Reference genome:**

**Human:** *GRCh38* or *hg38*

**Rattus norvegicus (Norway rat):** *Rnor6.0*

**Mouse:** *GRCm39* or *mm39*

