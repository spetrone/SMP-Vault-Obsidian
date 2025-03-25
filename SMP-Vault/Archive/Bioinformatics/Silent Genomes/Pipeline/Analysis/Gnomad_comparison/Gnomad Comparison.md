
Gnomad Hail Tables:
Genomes:
/mnt/scratch/SILENT/Act3/open_data/gnomad/v4.1/genomes/hail/gnomad.genomes.v4.1.sites.ht/
Joint:
/mnt/scratch/SILENT/Act3/open_data/gnomad/v4.1/joint/hail/gnomad.joint.v4.1.sites.ht/

Exomes:
/mnt/scratch/SILENT/Act3/open_data/gnomad/v4.1/exomes/hail/gnomad.exomes.v4.1.sites.ht

IBVL Hail Table (v37) - multi-split with bcftools
/mnt/scratch/SILENT/Act3/QC_Analysis/GRCh37-rerun/Input/SNV_vcf.mt

IBVL vcf - multisplit for liftover:
/mnt/scratch/SILENT/Act3/QC_Analysis/data/SGP/2023_1_1.0_GRCh37/pop_vcf/DeepVariant_GLnexus_Version_0.vcf.gz


IBVL Hail Table (v38) - not yet

HG002-4 vcf - 
/mnt/scratch/SILENT/Act3/open_data/HG002-4/processed/HG002-4_3.0/DeepVariant_GLnexus_HG002-4_GRCh38_3.0.vcf.gz

multi-split:
/mnt/scratch/SILENT/Act3/open_data/HG002-4/processed/HG002-4_3.0/DeepVariant_GLnexus_HG002-4_GRCh38_3_split.vcf.gz

```
import hail as hl
from bokeh.io import output_notebook, show
output_notebook()

recode = {"MT":"chrM", **{f"{i}":f"chr{i}" for i in (list(range(1, 23)) + ['X', 'Y'])}}
ibvl = hl.import_vcf('/mnt/scratch/SILENT/Act3/open_data/HG002-4/processed/HG002-4_3.0/DeepVariant_GLnexus_HG002-4_GRCh38_3_split.vcf.gz', force_bgz=True, reference_genome='GRCh38', contig_recoding=recode)

gnomad = hl.read_table('/mnt/scratch/SILENT/Act3/open_data/gnomad/v4.1/genomes/hail/gnomad.genomes.v4.1.sites.ht')

ibvl = hl.variant_qc(ibvl)
```


CHR22 - filtered freq only
/mnt/scratch/SILENT/Act3/QC_Analysis/data/SGP/2023_1_1.0_GRCh37/pop_vcf/SNV_filtered_frequ_only_22.vcf.bgz


/mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/84/ec1e61b6ff12604c6526c38ceeb2d1/

/mnt/scratch/SILENT/Act3/Processed/Workflow/Real_Data_August2023/Variant_catalogue_pipeline/work/95/f2f33a1f01936f87bc43c720a68995