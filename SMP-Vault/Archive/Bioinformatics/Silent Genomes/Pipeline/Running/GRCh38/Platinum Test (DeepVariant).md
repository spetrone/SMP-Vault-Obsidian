**

June 4

  

Input:

1st batch of 3 genomes in reads directory:

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194146_1.fastq.gz

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194146_2.fastq.gz

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194147_1.fastq.gz

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194147_2.fastq.gz

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194158_1.fastq.gz

/mnt/scratch/SILENT/Act3/Test_Data_Platinum_Genomes/reads/ERR194158_2.fastq.gz

  

Flow control

- main.nf: Commented out MT (remember sample_sex file dependency)
    
- SNV.nf : commented out
    

- Comment out everything except DeepVariant and list_vcf steps (trying this out)
    

- Removed comments from Mapping.nf so all steps q1-q5 are run
    

  
  

June 5

  

Ran all for first 3 successfully up until vcfs_to_text

- Note that mapping took a long time (18hrs)
    

  

-Now moving samples from batch 2 into main reads folder and resuming pipeline

- caching seems to be working

- BUT not updating (yet??) for QC steps beyond fastqc

  

June 7

- They all are listed in the vcf file
    
- Now uncommenting rest of SNV subworkflow and running
    

June 8

- Ran through SNV fine (need to check data)
    

**

June 11
- the XX/XY issue was resolved --> i.e. all were captured, none were anonymous
- now comparing with Aoteorea data and Illumina data