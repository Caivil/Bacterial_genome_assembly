# Bacterial_genome_assembly
## 1.Data source
The data was obtained from a public database from a study of Genome assembly of Pseudomonas aeruginosa YK01 using hybrid assembly of long and short reads. The data comprises of  single-end long reads and short paired-end reads sequenced with  Nanopore MinION sequencer Mk1B and  Illumina NextSeq 500 platform respectively. The subsamples are stored in Data/ which were used as inputs for the assembly workflow.
## 2.Obtaining the data
The long reads were obtaiend from the NCBI database and gunzip *.fastq.gz was used to unzip the file. 
The short reads were obtained with sratoolkit: ```module load sratoolkit.3.0.7``` then ```fasterq-dump SRR30916324 --split-files```.
## 3.Workflow
This workflow exaplains the hybrid de novo assembly of *Pseudomonas aeruginosa* YK01
### 3.1 Quality check
The tool ```fastqc``` was used to check the read quality . ```module load fastqc-0.11.7```  was ran to load the tool into the enivironmnet and the tool was ran:
<pre> fastqc SRR30916324_1.fastq
fastqc SRR30916324_2.fastq</pre>
Output is an ```.html``` file that you can view in your web browser. 
Trimming of low quality was then performed with ```trimmomatic-0.36``` for the paired-end reads:
<pre> java -jar $TRIMMOMATIC PE SRR30916324_1.fastq SRR30916324_2.fastq SRR30916324_1_paired.fastq SRR30916324_1_unpaired.fastq SRR30916324_2_paired.fastq SRR30916324_2_unpaired.fastq SLIDINGWINDOW:4:28 MINLEN:50 </pre>
Output is a trimmed ```.fastq``` file.
### 3.2 Hybrid de novo assembly




