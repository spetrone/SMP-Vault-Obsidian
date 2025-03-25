
- you can change the processes being run (i.e. comment them out)
- You CANNOT change the inputs to main.nf or to processes - that will cause the cache to break

- the clean function can fix the cache
	- if you revert the changes in the task script or input channels that caused the cache to break and use Nextflow clean to before the change, it will likely fix the cache
	
- the symlinks might actually be useful in the case of a broken cache - add them back + test Mapping out? or only re-introduce them if the cache breaks?
	- create an override cache functionality?