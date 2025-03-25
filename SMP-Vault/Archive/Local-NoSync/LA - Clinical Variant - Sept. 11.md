- adults entered as adults - likely to have way more siblings
- 7_151483594  GRCh37  C - T
- new publication 2% frequency 

`bcftools view -r 7:151483594 DeepVariant_GLnexus_Version_0.vcf.gz | bcftools view -i 'GT="alt"' | bcftools query -f "'[%CHROM:%POS %SAMPLE %GT\n]'" > output.txt

`awk ' $3=="0/1"  {print $2,$3}' output.txt `

F130119 0/1
F130550 0/1
F130564 0/1


F130119
`F130119 F130478 3rd`

F130550 
```
F130306 F130550 4th
F130535 F130550 3rd
F130544 F130550 FS
F130550 F130698 3rd
F130550 F130720 FS
```

F130564
```
F130564 F130720 4th
```

-------------
## Viewing BAM files on GPCC

---------------
Viewing with Samtools
TEST
```
unload_bcchr
load_cvmfs
module load samtools/1.20

cd 
samtools tview /mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/c5/a2cec888b8f7e5306a08811cb4b99a/F130550_sorted.bam /mnt/common/DATABASES/REFERENCES/GRCh37/GENOME/GRCh37-lite.fa -d C -p 7:151483594

samtools tview /mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/5b/ed86ecab3ff4b8601e1a81cef3a7ee/F130119_sorted.bam /mnt/common/DATABASES/REFERENCES/GRCh37/GENOME/GRCh37-lite.fa -d C -p 7:151483594


samtools tview /mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/da/44adfd1a39cbdffd4bd77a7cda02f9/F130564_sorted.bam /mnt/common/DATABASES/REFERENCES/GRCh37/GENOME/GRCh37-lite.fa -d C -p 7:151483594


#without variant: 
samtools tview /mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/cf/6affb1bce690de0572d697881ca8bb/F130784_sorted.bam /mnt/common/DATABASES/REFERENCES/GRCh37/GENOME/GRCh37-lite.fa -d C -p 7:151483594
```


bam files: `/mnt/scratch/SILENT/Act3/Processed/Individual/Real_Data_2023/GRCh37/Batch_2023-08-03/Version_0.0.2/ 













