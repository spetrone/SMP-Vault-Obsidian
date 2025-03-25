```
#!/bin/bash/

input_list="bamFilesList.txt"
tmp="sort_tmp.txt"
sheet="bam_sheet.csv"

rm $tmp
rm $sheet

touch $tmp
touch $sheet

declare -A hash         # associative array to tie basename with files

while read -r f
do
      #  base=${f%%_*}                     # for GSC - to change for bams 
    runName=${f##*Variant_catalogue_pipeline}
	baseFile=${runName##/*/}
	base=${baseFile%%_*}
	if [[ -z ${hash[$base]} ]]; then      # if the variable is not defined
        hash[$base]=",$f"     # then store the filename
		echo $base
    else
        hash[$base]+=",$f"    # else append the filename delimited by comma
    
	fi
done < $input_list

#write to csv sample sheet
for base in "${!hash[@]}"; do           # loop over the hash keys (basename)
    read -r f1 f2 <<< "${hash[$base]}"  # split into filename
        echo "$base$f1$f2" >> $sheet            #echo record and concatenate to sample sheet
done


#sort the file
sort $sheet > $tmp
cat $tmp > $sheet

```