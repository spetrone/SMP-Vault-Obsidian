#VCP

- Issue: GLI and GLI2 parameters were not the same as the outdir_ind
    
	- Needed to be the same as they are bound in singularity containers and GLNexus could not access the gvcf files it needed	    
	- Fix: set GLI to outdir_ind / make sure it is bound in the singularity container in the config file	    
	- Need to make this better!
	    
