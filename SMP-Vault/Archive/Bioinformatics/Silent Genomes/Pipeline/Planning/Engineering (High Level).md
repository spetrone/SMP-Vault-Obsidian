#VCP
1. **non-attributed code ?-double check + MIT Copyright
	- https://github.com/broadinstitute/gnomad_methods?tab=MIT-1-ov-file 
	- *Has MIT license and should be attributing: Konrad Karczewski, Laurent Francioli, Grace Tiao, Daniel MacArthur* and copying the MIT license
	- There may be more I am unaware of
2. Maintainability
	- documentation for containers
		- should ideally each have a YAML file so the containers can be re-created
	- documentation of code
		- change log?
		- tools
			- version
			- parameters and *why* parameters are used
		- data - inputs/outputs/amount of data
	- documentation of runs
1. **Dependencies**
	- *MT  & SV- SNV subworkflow dependency* with sex file created in SNV sub-workflow - requires that sub-workflow mostly completes before MT & SV also means they are not disjoint
	- more? 
2. **Lack of Modularisation**
	1. Pipeline Modularisation - not modular without a lot of work 
		1. flow control issues
			1. currently there are issues with incorrectly using features for flow control that are not meant for flow control:
				1. exception handlers
				2. commenting out pipeline subworkflows to control flow through another
					1. causes issues with Nextflow cache and -resume function 
	2. Code Modularisation
		1. Python/Gnomad Methods
			- there are *code modules*
			- but the *pipeline is not modular* 
1. **Lack of Portability** 
	- Hard-coded file names & file paths
		- this is throughout the pipeline, in almost every file
		- will have multiple levels of scripts calling scripts, searching file paths, building text files of filepath names, and parsing strings
	- More containerisation is needed (R, HAIL)