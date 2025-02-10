# RNA-seq alignment

# **Link:**

Hisat2 (https://daehwankimlab.github.io/hisat2/)

# **Script:**

#!/bin/bash 
/ngs/programas/hisat2-2.1.0/hisat2 -p 7 -q --dta -x /ngs/genomas_ref/Rattus_norvegicus/hisat2_index/Rattus_norvegicus.Rnor_6.0.dna.toplevel -1 SUB_1_1.fastq.gz -2 SUB_1_2.fastq.gz -S alinha_sub1.sam

# **Script explanation:**

**#!/bin/bash:** This file is going to be executed

**/ngs/programas/hisat2-2.1.0/hisat2:** Path location of the HISAT2 program. In this case, the software is located at */ngs/programas/hisat2-2.1.0*

**-p 7**: It specifies the number of CPU threads to use. In this case, 7 threads

**-q:** It indicates that the input files are in FASTQ format

**--dta:** It means "downstream transcriptome analysis" and tells HISAT2 to report alignments tailored for transcript assemblers

**-x /ngs/genomas_ref/Rattus_norvegicus/hisat2_index/Rattus_norvegicus.Rnor_6.0.dna.toplevel:** It specifies the path to the HISAT2 index for the reference genome of Rattus norvegicus

**-1 SUB_1_1.fastq.gz -2 SUB_1_2.fastq.gz:** It specify the paired-end read files in FASTQ format. *-1 is for the first pair (SUB_1_1.fastq.gz)*, and *-2 is for the second pair (SUB_1_2.fastq.gz)*

**-S alinha_sub1.sam:** It specifies the output file name. The aligned reads will be saved in the SAM format file named *alinha_sub1.sam*

# **Reference genome:**

**Human:** *GRCh38* or *hg38*

**Rattus norvegicus (Norway rat):** *Rnor6.0*

**Mouse:** *GRCm39* or *mm39*

# Transforming .sam into .bam files:

The final files are in *.sam* format, but they are very large and therefore need to be converted to *.bam* format. BAM files are compact and save storage space, in addition to being faster to read and write. If its is necessary, the programmer can remove the *.sam* format files to save storage space using the command **rm name_of_file**


# Script:

#!/bin/bash
samtools view -Su  alinha_sub1.sam > alinha_sub1.bam
samtools sort alinha_sub1.bam > alinha_sub1.sort.bam


# Script explanation:

**#!/bin/bash:** This file is going to be executed

**samtools view:** the command to view and convert the SAM file

**-S:** it indicates that the input format is SAM

**-u:** it produces an uncompressed BAM output

**alinha_sub1.sam:** it is the input SAM file

**>** redirects the output to alinha_sub1.bam, which is the output BAM file

**samtools sort:** it is the command to sort the BAM file

**alinha_sub1.bam:** it is the input BAM file

**>** redirects the output to alinha_sub1.sort.bam, which is the sorted BAM output file
