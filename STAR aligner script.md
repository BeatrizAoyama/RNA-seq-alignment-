# RNA-seq alignment

Link:
STAR (https://github.com/alexdobin/STAR)


# **Script:**

#!/bin/bash

STAR --runThreadN 7 --genomeDir /file/genomas_ref/GRCh38/ --readFilesCommand gunzip -c --readFilesIn SUB_9_1.fastq.gz   --quantMode GeneCounts --outFileNamePrefix ./sub9/ --genomeLoad LoadAndKeep


# **Script explanation:**


**#!/bin/bash:** This file is going to be executed

**STAR:** Command to call the STAR software

**--runThreadN 7:** Specifies the number of threads to be used during execution. In this case, 7 threads are used to speed up the alignment process

**--genomeDir /file/genomas_ref/GRCh38/:**  Specifies the directory where the reference genome is located. In this example, the path is ***/file/genomas_ref/GRCh38/***

**--readFilesCommand gunzip -c:**  Specifies the command to be used for decompressing compressed files. In this case, **gunzip -c** is used to decompress ***.fastq.gz files***

**--readFilesIn**SUB_9_1.fastq.gz:**  Specifies the input file(s) containing the sequencing reads. In this example, the input file is ***SUB_9_1.fastq.gz***

**--quantMode GeneCounts:**  Activates the gene quantification mode, which counts the number of reads mapped to each gene

**--outFileNamePrefix./sub9/:**  Specifies the prefix for the output files. In this example, the output files will be stored in the directory ***./sub9/***

**--genomeLoad LoadAndKeep:**  Specifies that the reference genome should be loaded into shared memory and kept there for future STAR runs


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

**>**  redirects the output to alinha_sub1.sort.bam, which is the sorted BAM output file


