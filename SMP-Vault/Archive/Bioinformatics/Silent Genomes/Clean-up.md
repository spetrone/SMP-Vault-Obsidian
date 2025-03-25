To do:
- delete last directory that failed from Individual
- 

1. Individual
(before)
check_quota
![[Pasted image 20241030102343.png]]
df -h
![[Pasted image 20241030102524.png]]

script:
```
  1 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Bench/                                                                                
  2 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Develop_merge_test_November2023/
  3 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/HG002-4_GRCh38_1.0/
  4 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/kiana_cancellation_test/
  5 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/kiana_intermediate_storage_usage/
  6 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Kiana_Pipeline_Dev_Summer24/
  7 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Mohammed_Test_Dec2023_GRCh37/
  8 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Phil_Test_August2023/
  9 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Phil_Test_July_2023/
 10 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Platinum_Test_June_2024/
 11 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/test/
 12 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/test3/
 13 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_April_2023/
 14 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_August_2023/
 15 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_August_2023_GRCh38/
 16 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_June_2023/
 17 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_September_2023_GRCh37/
 18 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/Test_September_2023_GRCh38/
 19 rm -rf /mnt/scratch/SILENT/Act3/Processed/Individual/data/Variant_catalogue_pipeline/

```
(after)
first attempt - line 19 failed (/mnt/scratch/SILENT/Act3/Processed/Individual/data/Variant_catalogue_pipeline/) -- permission denied -- however its sub-directors and files were all deleted succesfully

![[Pasted image 20241030105111.png]]

![[Pasted image 20241030105130.png]]



2. Population
(before)
![[Pasted image 20241030123549.png]]
![[Pasted image 20241030123612.png]]
script:
```  1 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Develop_merge_test_November2023/
  2 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/HG002-4_GRCh38_1.0/
  3 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/kiana_intermediate_storage_usage/
  4 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/kiana_platinum_update/
  5 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Kiana_Updated_IBVL_Frequencies_June_2024/
  6 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Mohammed_Test_Dec2023_GRCh37/
  7 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Phil_Test_July_2023/
  8 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Platinum_Test_June_2024/
  9 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Test_April_2023/
 10 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Test_August_2023_GRCh38/
 11 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Test_June_2023/
 12 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Test_September_2023_GRCh37/
 13 rm -rf /mnt/scratch/SILENT/Act3/Processed/Population/Test_September_2023_GRCh38/  
```

result: OK

(After):
![[Pasted image 20241030124107.png]]

![[Pasted image 20241030124141.png]]

3. Workflow dirs
(before)
![[Pasted image 20241030130754.png]]
![[Pasted image 20241030130820.png]]
(after)
![[Pasted image 20241030133324.png]]
![[Pasted image 20241030133345.png]]