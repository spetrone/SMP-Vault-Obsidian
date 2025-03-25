Refer to [BAM Entry point](obsidian://open?vault=SMP-Vault&file=Bioinformatics%2FSilent%20Genomes%2FPipeline%2FDevelopment%2FBAM%20entry%20point)

1. Create csv file:

`readlink -f  < bam directory >/* all_SG_v1_bam_file_list.txt
actual 
`readlink -f /mnt/scratch/SILENT/Act3/Processed/Individual/2024_1_1.0_GRCh38/GRCh38/sample_set_v01/2024_1_1.0_GRCh38/BAM/*  > all_SG_v1_bam_file_list.txt

`awk '{printf $0 ","; getline; print}' all_GSC_bam_file_list.txt > all_SG_v1_bam_tuples.csv

2. Extract samples to make individual sample sheets with:
```
sed -n '1,20p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_01.csv
```

---------------- 
Code Changes

1. main.nf - uncommented SNV (left inputs as is to preserve cache)
2. subworkflow SNV.nf 
	- added channel factory above take: 
	 ` bam_ch = Channel.fromPath(params.bam_sheet)
        `.splitCsv()
        `.map { row -> tuple(file(row[0]), file(row[1])) }`
    - changed names of take:, made redundant as to preserve input to process to preserve cache, to old_bam and old_bai
    - changed 3rd/4th arg of deepvariant_call() to the one bam_ch
	    `deepvariant_call(reference, reference_index, bam_ch, assembly, batch, run)
`
1. changed deepvariant.nf
	- changed input: for third argument to be tuple:
```
 15     input :
 16     file reference
 17     file reference_index
 18     tuple path(bam), path(bai)
 19     val assembly
 20     val batch
 21     val run

```
	


------------------------------------ 

Copy command:
scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/samplesheets/bam/sheets/bam_sheet_batch_09.csv /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/bam_sheets/

---- 1/9 .nextflow logs
1. Batch 01: sed -n '1,20p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_01.csv
	- 20 samples
	- slurm job: 231149
	- nextflow
	- 2/9 nextflow logs
1. Batch 02: sed -n '21,60p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_02.csv
	 - 40 samples
	 - slurm job: 231213 
	 - nextflow:
	 - 3/9 nextflow logs
1. Batch 03: sed -n '61,140p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_03.csv
	- 80 samples
	- slurm job: 231270
	- nextflow : [agitated_mccarthy]
	- 4/9 .nextflow logs
1. Batch 04: sed -n '141,220p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_04.csv
	- 80 samples
	- slurm job: 231432
	- nextflow :  [sharp_tesla] - revision: f266102f66
	- 5/9 .nextflow logs
1. Batch 05: sed -n '221,300p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_05.csv
	- 80 samples
	- slurm job: 231577
	- nextflow: [determined_kilby] - revision: f266102f66
	- 6/9 .nextflow.logs 
1. Batch 06: sed -n '301,380p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_06.csv
	- 80 samples
	- slurm job: 231763
	- nextflow: [drunk_brenner] - revision: f266102f66
	- 7/9 .nextflow.logs
1. Batch 07 : sed -n '381,460p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_07.csv
	- 80 samples
	- slurm job:  231892
	- nextflow: [awesome_cantor] - revision: f266102f66
	- 8/9 .nextflow.logs
1. Batch 08 : sed -n '461,540p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_08.csv
	- 80 samples
	- slurm job:  232122
	- nextflow:  [romantic_bell] - revision: f266102f66
	- 9/9 .nextflow.logs
*** logs put into: ./log_archive/batch_02/
1. Batch 09 :  sed -n '541,596p' all_SG_v1_bam_tuples.csv > bam_sheet_batch_09.csv
	- 56 samples
	- slurm job: 232327
	- nextflow: [ecstatic_leavitt] - revision: f266102f66
	- 1/9 .nextflow logs:

Batch 08 ![[Pasted image 20241024180436.png]] 
![[Pasted image 20241025111706.png]]