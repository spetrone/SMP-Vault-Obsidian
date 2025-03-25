Alex TLS  job20   - job20


- Create project with name
- Drag file

- Register using:
	- Auto Sphere Target (the white balls)
	- Import Images (takes point clouds and pictures of the scan)
	- select Import -> it will automatically import all the scans


- show in setup cloud view to see from the ground view
- link scans to create bundles
- edit target
	- select the white ball, and write down the number on the target
	- three targets need to be shared to make a link
- then select the jobs and "match target"
	- can also try with auto-cloud, particularly if you have high error or low strength
- to improve error
	- visual alignment --> optimize alignment

- quality check for good scan
	- TruSlicer - zoom in the ground and look for full circles
	- can right click and join and optimize bundle - be careful with the automatic stuff
- can block a link
	- then it won't change that link
	- to do so --> click bundle, lock is a toggle in properties and you can lock a whole bundle

- handling a bad scan
	- split view - will give point cloud from both
		- then select each point in each view - they don't have to be targets


- automatic cloud-to-cloud - link the scans automaticall - very time consuming and to import/export and we don't need it


#### Finalize
- once links are made and any optimization is done and error is okay then select finalize from the top bar
- beforeo you can clip it in review and optimize, 
- select accept
	- there is a report
- select publish options
	- select LAS for TreeQSM