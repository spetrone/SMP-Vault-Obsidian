nextflow config:
```
params.filter_samples   = true
params.filter_list      = "/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.1_GRCh38/filter_samples/2024_1_1.1_GRCh38_filter_samples.tsv" 
```

main.nf
- comment out sample sheet input
- comment out all sub-workflows except SNV
- remove arguments from SNV

SNV.nf
- comment out take (bam and bai) -
- add channel factory here to take GLNexus file from input directory
`GLnexus_bcf = Channel.fromPath('/mnt/scratch/SILENT/Act3/Processed/Workflow/2024_1_1.1_GRCh38/input/DeepVariant_GLnexus_2024_1_1.0_GRCh38.bcf')`
- comment out everything up to and including GlNexus
- change bcf_to_vcf arg to the channel created with the bcf (GLnexus_bcf_)


SLURM JOB#: 247211
Nextflow ID: determined_lumiere