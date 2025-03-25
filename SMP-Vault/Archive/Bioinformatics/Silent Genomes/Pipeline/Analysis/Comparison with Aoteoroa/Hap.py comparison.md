
From Ben:

I’ve generated some comparisons between our current DV calls and put them into HG002_CallComparisons/2024_07_20_GLN_DV_NonKrakened_vs_DeepVariant_GLnexus_HG002-4_GRCh38_3.0

I’ve done these comparisons both ways (UoO or UBC as the baseline) based on HG002, so there are two directories. I modified your contig naming to bring it into alignment with ours (using ‘chr1’) and restricted to just the autosomes (as we’ve included unmapped contigs etc., you’ve got MT calls, and we’ve done postprocessing on chrX/Y for males).

We have pretty good concordance (UoO-UBC, F=0.9805, Sens=0.9837, Prec=0.9773), see the summary.txt and the rocplots (based on HG002 GQ). I haven’t done any formal follow up analyses, but it looks like a lot of the discordance is in low quality calls (GQ < 20) and in multiallelic repeat sites, as would be expected. I’ll generate some more detailed stats, but I thought you might like the data available beforehand.

David brought up something important last week - we don’t know the intra-pipeline variability for these calls (variability at alignment, variant calling, and any other step along the way). So, we don’t know the background variability expected when doing these inter-pipeline comparisons. We’ll have a go generating a couple of calls on the HG002 data and see how different they are. 