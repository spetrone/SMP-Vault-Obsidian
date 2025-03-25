- run the setup script from TreeLearn
- re-install pytorch (uninstall, the conda install)
	``` 
	conda uninstall pytorch
	conda install pytorch
```
- find CUDA version & install spconv for that version (pip3
	- `python3 -m pip install spconv-cu118
	- it is Cuda11.8
- install Jakterastics
	- `python3 -m pip install jakteristics`