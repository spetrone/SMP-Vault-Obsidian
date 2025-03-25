#VCP
- Is the automatic flow of processes OK? Should we set any conditions to wait for certain processes to be done before starting downstream processes?
	- e.g. finish Hail_variant_QC before commencing downstream data organization?
- Hard-coded and absolute file paths used throughout. 
	- searching using the `find .` command should not be done
	- .txt files with filenames are being used instead of channels (specifically for GLNexus)
	- Parsing of absolute filepath names causing errors - `sed` command used incorrectly
	- idea - use tuple channels with chromosome + filepath instead of parsing file names to get chromosome  
- **Symbolic links** used throughout and are redundant
	- Nextflow --resume and caching covers this;
	- It is done in a weird fashion anyways; it ends up creating symlink --> symlink --> file
	
- **Nextflow Configuration** 
	- needs better documentation
	- there need to be usage instructions that explain configuration better
	- Bind paths for GLNexus in config file are not documented (GLI and GLI2)
	- 
- **Spark configuration** - nothing has been done; I am guessing that Spark is the root cause of the memory issue Phil refers to (although I did not recreate it)
	- or perhaps memory issue is related to exception handlers being used for flow control in hail scripts affecting Spark since it uses Spark. 
	
- Variants
	- Is the pipeline adequately performing QC - i.e. is filtering by standard deviations enough
	- Is there any unexpected behaviour occurring by running it in batches (~80 is supposedly what  Phil did), when the pipeline is not constructed to work that way and so this process of running in batches is falling back on Nextflow caches/the resume function and the code that expects one distinct batch