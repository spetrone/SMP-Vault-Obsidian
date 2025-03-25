
Samplesheets

batch_01: sed -n '1,40p' all_GSC_SGP_samples.txt> sample_sheet_batch_01.txt
	- 20 samples
batch_02: sed -n '41,120p' all_GSC_sampleset_01.txt > sample_sheet_batch_02.txt
	- 40 samples
batch_03:  sed -n '121,280p' all_GSC_sampleset_01.txt > sample_sheet_batch_03.txt
	 - 80 samples
batch_04: sed -n '281,440p' all_GSC_sampleset_01.txt > sample_sheet_batch_04.txt
	 - 80 samples
	 - job: 227737 
batch_05: sed -n '441,600p' all_GSC_sampleset_01.txt > sample_sheet_batch_05.txt
	- 80 samples
	- job: 228332
batch_06: sed -n '601,760p' all_GSC_sampleset_01.txt > sample_sheet_batch_06.txt
	- 80 samples
	- job: 228859
batch_07: sed -n '761,920p' all_GSC_sampleset_01.txt > sample_sheet_batch_07.txt
	- 80 samples
	- job 229373 (error caused crash with this)
batch_08: sed -n '921,1080p' all_GSC_sampleset_01.txt > sample_sheet_batch_08.txt
	- 80 samples
	- job 229939
	
--- 9 .nextflow.logs hit (less for other log files), so archived them, after completing
 Variant_Catalogue_v1.sh-229939.out. Archived in 
`/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/run_A/Variant_catalogue_pipeline/log_archive/batch_01`

batch_09: sed -n '1081,1192p' all_GSC_sampleset_01.txt > sample_sheet_batch_09.txt
	- 56 samples
	- job 230495
--- 1 .nextflow logs added

Copy command:
scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/samplesheets/fastq/sample_sheet_batch_09.txt /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/fastq_sheets/

scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/samplesheets/fastq/sheets/sample_sheet_batch_09.csv /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/fastq_sheets/




--- 
Copy error logs:
--- --- 
scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/run_A/Variant_catalogue_pipeline/.nextflow.log.1 /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/logs/

scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/run_A/Variant_catalogue_pipeline/trace.txt.1 /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/logs/


scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/run_A/Variant_catalogue_pipeline/Variant_Catalogue_v1.sh-229373.error /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/logs/

scp stephanie.petrone@gpcc-node01:/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.0_GRCh38/run_A/Variant_catalogue_pipeline/Variant_Catalogue_v1.sh-229373.out /home/linuxuser/bioinfo/SGP/2024_1_1.0_GRCh38/logs/

---

