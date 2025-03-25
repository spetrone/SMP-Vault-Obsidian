
- see code in /mnt/scratch/SILENT/Act3/Real_Data_Processing/Platinum_Test_Data_Run_A/Workflow/Variant_catalogue_pipeline 
- By following this, the cache should not be broken
- Can use and add to sample sheet the way the fastq sample sheets are currently used (and tested) - maintains cache


Create csv file:

`readlink -F * < bam directory >  > bamFileList.txt

`awk '{printf $0 ","; getline; print}' bamFileList.txt > bamFileTupleList.txt



Changes to be made:
- add a sample sheet for bams - tuple of (.bam, .bai) in csv, no spaces
- change SNV.nf
```
	//Add this channel factory
	//Trying out BAM sample sheets
    bam_ch = Channel.fromPath(params.bam_sheet)
        .splitCsv()
        .map { row -> tuple(file(row[0]), file(row[1])) }
        .view()

	//change name of old inputs - will keep channel, but will not use them
    // Workflow start here
    take : 
        bamOld
        baiOld

```
this method makes Nextflow channels redundant - they are there but not used; since just symlinks

Also change the deep variant call (replace bam, bai inputs with one - the bam_ch):
```
main :
        // Sample specific (Do not need to be run for a previously processed sample)
        deepvariant_call(reference, reference_index, bam_ch, assembly, batch, run)


```
- change the deepvariant.nf module:
```
//change the input to replace the separate bam and bai file paths with 
// on tuple (same as input and same order as in the deepvariant_call() in SNV.nf)
    input :
    file reference
    file reference_index
    tuple path(bam), path(bai)
    val assembly
    val batch
    val run 

```

Changes to avoid:
- do not change main.nf
	- changing inputs in tasks called in main seem to break the cache for everything - even if changing the SNV input, it breaks the cache for the mapping step before it (possibly affects hash of output?)
	- this means keeping the input channels to the SNV process call



----------------------- 
Creating csv

- create a csv with BAMS using [script](obsidian://open?vault=SMP-Vault&file=Bioinformatics%2FSilent%20Genomes%2FPipeline%2FDevelopment%2Fbam_csv_script)
- copy sample_sex tsv from work directory of run in question


- turn sample_sex file from tsv to csv
sed -i -e 's/\t/,/g' filename

alternative - turn csv to tsv before join

`awk -F ',' 'BEGIN {OFS="\t"} {$1=$1}1' bam_sheet.csv > bam_sheet.tsv 

- merge with sample sex tsv

as tsv
`join bam_sheet.tsv sample_sex.tsv > full_bam_sheet.tsv`

as csv
`join sample_sex.csv bam_sheet.csv -t , > full_bam_sheet.csv`




DV TEST samplesheets location with scripts:
/mnt/scratch/SILENT/Act3/QC_Analysis/Deepvariant_testing/DV_GRCh38_HG002-4_01/samplesheets

Nextflow testing:
/mnt/scratch/WassermanLab/spetrone/scripts/nextflow_tests


--------------------------- 
CHANGES TO BE MADE IF USING SAMPLE SEX
-------------------------------------------------------
(NOTE: Deepvariant v1.6.1 not currently working with Nextflow due to an error in post-processing with file globbing - multiple files with same pattern - need to somehow have the post-processing execute from a directory and read only one set of files (not sure which))
- use csv as created above:
```
bam_ch = Channel.fromPath("./full_bam_sheet.csv")
        .splitCsv()
        .map { row -> tuple("${row[0]}","${row[1]}","${row[2]}", "${row[3]}") }
        .view()

```

with file paths as files in nextflow lang:
```
bam_ch = Channel.fromPath(params.bam_sheet)
        .splitCsv()
        .map { row -> tuple("${row[0]}","${row[1]}",file(row[2]), file(row[3])) }
        .view()
```
maybe take out the .view()

then in input
list is as :
`tuple val(sample_name), val(sample_sex), path(bam), path(bai)`