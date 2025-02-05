# RNA-seq alignment

Link:
STAR (https://github.com/alexdobin/STAR)


Script:

#!/bin/bash

STAR --runThreadN 7 --genomeDir /file/genomas_ref/GRCh38/ --readFilesCommand gunzip -c --readFilesIn SUB_9_1.fastq.gz   --quantMode GeneCounts --outFileNamePrefix ./sub9/ --genomeLoad LoadAndKeep


Script explanation:

STAR: Command to call the STAR software

**--runThreadN 7:** Specifies the number of threads to be used during execution. In this case, 7 threads are used to speed up the alignment process

**--genomeDir /file/genomas_ref/GRCh38/:** Specifies the directory where the reference genome is located. In this example, the path is **/file/genomas_ref/GRCh38/**

**--readFilesCommand gunzip -c:** Specifies the command to be used for decompressing compressed files. In this case, **gunzip -c** is used to decompress **.fastq.gz files**

**--readFilesIn**SUB_9_1.fastq.gz: Specifies the input file(s) containing the sequencing reads. In this example, the **input file is SUB_9_1.fastq.gz**

**--quantMode GeneCounts:** Activates the gene quantification mode, which counts the number of reads mapped to each gene

**--outFileNamePrefix** ./sub9/: Specifies the prefix for the output files. In this example, **the output files will be stored in the directory ./sub9/**

**--genomeLoad LoadAndKeep:** Specifies that the reference genome should be loaded into shared memory and kept there for future STAR runs


Reference genome:

**Human:** GRCh38 or hg38.

**Rattus norvegicus (Norway rat):** Rnor6.0

**Mouse:** GRCm39 or mm39
