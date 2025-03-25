```
#!/bin/bash

#SBATCH --mail-user=stephanie.petrone@bcchr.ca
#SBATCH --mail-type=ALL

#SBATCH --partition=defq

#SBATCH --time=30:00:00
#SBATCH --nodes=1

#SBATCH --cpus-per-task=12
#SBATCH --mem=96G

#SBATCH --job-name=king
#SBATCH --output=king-%j.out
#SBATCH --error=king-%j.error


#plink software
plink="./plink"
king="./king"

#---------------
# R for king --rplot flag
#---------------
unload_bcchr
load_vcmfs
module load StdEnv/2020
module load gcc/9.3.0
module load r/4.0.5
export R_LIBS=/mnt/scratch/Public/Rstudio/spetrone/R_Libs_4.0.5/


#source conda
source /mnt/scratch/WassermanLab/spetrone/Software/Miniconda3/miniconda3/etc/profile.d/conda.sh

conda activate somalier

# ------ GRCh37 ------
ref_v37="/mnt/common/DATABASES/REFERENCES/GRCh37/GENOME/GRCh37-lite.fa"
SGP_GRCh37_vcf="/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/data/2023_1_1.0_GRCh37/DeepVariant_GLnexus_Version_0.vcf.gz"


# -------- GRCh38 --------
ref_v38="mnt/common/DATABASES/REFERENCES/GRCh38/GENOME/GRCh38.p14/PrimaryChromOnly/GRCh38.p14_PrimaryOnly.fa"

#create plink binary files for king (required by king)
#$plink --vcf $SGP_GRCh37_vcf --vcf-half-call missing  --make-bed --out sgp_37

# KING requires (# of SNPS * # of samples ) bytes of memory, plus some overhead, to run. For us, that is around 20GB minimum. 
$king -b sgp_37.bed --related --degree 4 --rplot
```