# Bacterial_genome_assembly
## 1.Data source
The data was obtained from a public database from a study of Genome assembly of Pseudomonas aeruginosa YK01 using hybrid assembly of long and short reads. The data comprises of  single-end long reads and short paired-end reads sequenced with  Nanopore MinION sequencer Mk1B and  Illumina NextSeq 500 platform respectively. The subsamples are stored in Data/ which were used as inputs for the assembly workflow.
## 2.Obtaining the data
The long reads were obtaiend from the NCBI database and gunzip *.fastq.gz was used to unzip the file. 
The short reads were obtained with sratoolkit: ```module load sratoolkit.3.0.7``` then ```fasterq-dump SRR30916324 --split-files```.
## 3.Workflow
This workflow exaplains the hybrid de novo assembly of Pseudomonas aeruginosa YK01
### 3.1 quality check
The tool '''fastqc''' was used to 
module load fastqc-0.11.7
fastqc SRR30916324_1.fastq
fastqc SRR30916324_2.fastq
