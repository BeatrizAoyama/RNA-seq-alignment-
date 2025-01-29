# RNA-seq alignment

The first step in starting the analysis of RNA-seq data is genomic alignment. This process uses an annotated reference transcriptome to map the sequenced reads, which are in FASTQ format, to the reference genome. Genomic alignment establishes the origin of the reads in the genome and quantifies the number of reads aligned at each position of the reference genome.

There are several different types of aligner softwares, but here I am going to describe three of them: 

STAR (https://github.com/alexdobin/STAR)

HISAT2 (https://github.com/DaehwanKimLab/hisat2) 

Kallisto (https://github.com/pachterlab/kallisto)
