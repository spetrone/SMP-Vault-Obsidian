
- Providing the R path to King and exporting it to the environment variable does not seem to work on the compute cluster. However, running it in an interactive session with the following commands works well:

- note on ages
- from: https://cahhm.mcmaster.ca/first-nations-cohort-participants/ 
|Age, years (mean [SD])*|   |1302|45.5 (13.4)|48.6 (12.0)|44.2 (14.2)|49.1 (12.4)|48.2 (10.0)|43.0 (15.5)|40.9 (13.0)|49.4 (12.2)|38.6 (13.2)|

## 1. Instructions

----- running R for KING -------
salloc --mem=64G

unload_bcchr
load_cvmfs
module load StdEnv/2020
module load gcc/9.3.0
module load r/4.0.5
export R_LIBS=/mnt/scratch/Public/Rstudio/spetrone/R_Libs_4.0.5

Then run:


-----mounting ------------------ 
- to view the results (R plots) 

sshfs stephanie.petrone@gpcc-node01.bcricwh.lan:/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/independent_set/mnt  /home/linuxuser/bioinfo/SGP/mnt

NEED PARALLEL REUNNIG TOO
## 2. Location of data, analysis, results:
### 2.1 Directories

- All Relatedness directories: 
	`/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness 
	
- Input data (vcf from GLNexus with multi-allelics split): 
	- 2023_1_1.0_GRCh37:  `/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/data/2023_1_1.0_GRCh37 
- Analysis Directory:
	- `/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/KING`
- Results directory:
		`/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/KING/results/2023_1_1.0_GRCh37/king_related_deg_4`

### 2.2 Method
#### 2.2.1 Pre-processing:
- Plink1.9 was used to create plink binary files:
- command:
	`$plink --vcf $SGP_GRCh37_vcf --vcf-half-call missing  --make-bed --out sgp_37`
#### 2.2.2 KING
 - KING version **2.3.2** (released on September 8, 2023) was used
 - this option run as it has the most information on deg 1-4 relationships (although only deg. 1 end up being used for filtering):
	`$king -b sgp_37.bed --related --degree 4 --rplot`
#### 2.2.3 [Script](obsidian://open?vault=SMP-Vault&file=Local-NoSync%2FRelatedness%2Fscript)

##### 2.2.4  [King Output](obsidian://open?vault=SMP-Vault&file=Local-NoSync%2FRelatedness%2FKing%20output)

## 3. Summary of Results

Pairs of relative (up to 4th degree): 1070
Dup/MZ: 1 (F130716	F130730)
1st: PO:0; FS: 141
2nd: 328
3rd: 600
4th: 0


##  4. Maximum Independent Set 
To reduce the number of samples to filter, I calculated a maximum independent set, the complement of which will be filtered.
Method 1: networkx maximal_independent_set (non-deterministic)
Method 2: networkx.approximation.maximum_independent_set (deterministic, slightly less optimal)

method scripts [here](obsidian://open?vault=SMP-Vault&file=Local-NoSync%2FRelatedness%2Fscripts%2FIndependent%20set%20scripts)
Both were run with a metaheuristic, 10,000 times, with the largest set being kept (mostly needed for maximal independent set as the set sizes differed between executions)

##### FILES & DIRECTORIES

- Input Files: (note file (c) was the file used for analysis)
Located: `/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/independent_set 



how it was sourced: taking the results from here (`/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/KING/results/2023_1_1.0_GRCh37/king_related_deg_4/king.kin0`)
	- step 1: those with an inferred relationship of "FS" and "Dup/MZ,  PO" were extracyed from this file, which is 236 relationship pairs that are first degree (FS = full sibling) or duplicate/monozygotic twins (1 of such pairs) or Parent offspring (PO). Columns extracted were ID1, ID2, and InfType.
	- step 2: samples filtered out during hail sample QC were removed (specifically there were 2). Therefore 142 - 2 = 140 remaining first degree or MZ/Dup pairs. 
- using this:
```
head -n 1 king.kin0 | awk ' {print $2,$4,$14} ' > 2023_1_1.0_GRCh37_deg1_pairs.tsv

awk ' $14=="PO" || $14=="FS" || $14=="Dup/MZ"  {print $2,$4,$14} ' king.kin0 >> 2023_1_1.0_GRCh37_deg1_pairs.tsv

awk 'NR==FNR {filter[$1]; next} !($1 in filter)'  samples_filtered_qc.tsv 2023_1_1.0_GRCh37_deg1_sample_pairs.tsv > output.tsv
```



- Analysis Directory with scripts in .py files and png `/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/independent_set
	- specifically this sub-directory: ``/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/independent_set/maximum_set_QC_filtered
	- 
 - graph png directory with copies for /mnt/:
	 - `/mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/independent_set/mnt

- Outputs:
	- TSV files with independent set (max_ind_set.tsv), and related samples to filter (rel_samples_to_filter.tsv)
	- plotted graph of first degree relatedness (first_degree_graph.png)
	- plotted graph of first degree relatedness with maximal independent set in red (max_ind_graph.png)

Summary (in graph_info file)
Number of nodes total: 186
Number of samples in the maximum independent set: 81
Number of samples to be filtered: 105
Number of first degree relationships (edges): 140



## 5. Summary of Tool & Inference Method (KING)
