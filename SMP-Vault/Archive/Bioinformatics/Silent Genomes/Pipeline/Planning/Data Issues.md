- number of variants ~20M (our gnomad file)
- gnomad release V2.1.1  ~250M , 17M exomes - SNVs and INDELS

- more anlaysis needed for comparing to gnomad frequencies

- Variant calling
	- how is data normalized?
	- how are multi-allelic variants split?
		- using this code
```
bcftools view ${bcf_file} | bgzip -c > ${bcf_file.simpleName}.vcf.gz
bcftools norm -m -any -o ${bcf_file.simpleName}_norm.vcf ${bcf_file}
bcftools annotate --set-id '%CHROM\\_%POS\\_%REF\\_%FIRST_ALT' -O z -o ${bcf_file.simpleName}.vcf.gz ${bcf_file.simpleName}_norm.vcf
```

specifically ` bcftools norm -m -any -o `

According to bcftools documentation:
**-m, --multiallelics** **-**|**+**[_snps_|_indels_|_both_|_any_]

split multi-allelic sites into bi-allelic records (**-**) or join biallelic sites into multiallelic records (**+**). An optional type string can follow which controls variant types which should be split or merged together: If only SNP records should be split or merged, specify _snps_; if both SNPs and indels should be merged separately into two records, specify _both_; if SNPs and indels should be merged into a single record, specify _any_.    
   
Note that multiallelic sites with both SNPs and indels will be split into biallelic sites with both **-m -snps** and **-m -indels**.


seems to split multi-allelic sites, but replace ALT with REF (0) rather than .