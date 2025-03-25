CONDA
source /mnt/scratch/WassermanLab/spetrone/Software/Miniconda3/miniconda3/etc/profile.d/conda.sh

conda activate biostar

COPY
scp stephanie.petrone@gpcc-node01.bcricwh.lan:/source /home/linuxuser/bioinfo/SGP/mnt

MOUNT
sshfs stephanie.petrone@gpcc-node01.bcricwh.lan:/source /home/linuxuser/bioinfo/SGP/mnt



## JUPYTER on GPCC

GPCC:

salloc --cpus-per-task=32 --mem=256GB --partition=silent_q
salloc --cpus-per-task=39 --mem=280GB --partition=silent_q

salloc --cpus-per-task=16 --mem=128GB
source /mnt/scratch/WassermanLab/spetrone/Software/Miniconda3/miniconda3/etc/profile.d/conda.sh
conda activate hail_analysis
jupyter-notebook --no-browser --port=8888

LOCAL MACHINE:
ssh -N  -L localhost:8889:localhost:8888 stephanie.petrone@gpcc-node02.bcricwh.lan

You can open one of the listed URLs (in the shell on GPCC) on your local machine, except change 8888 for 8889 (see step 5).



COPY MT

find .


