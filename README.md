# CUDA Examples

To run these examples you'll need to run an interactive SLURM job on one of the Maxwell GPU nodes:

	$ salloc --partition=maxwell --account=sc3260 --time=2:00:00 --gres=gpu:1

This will give you one CPU core and one NVIDIA Titan X Maxwell GPU. Alternatively, you may use
the provided SLURM script (single-gpu.slurm) and submit it through SLURM with:

	# sbatch single-gpu.slurm

Just copy the file to the appropriate directory and make sure to insert the name of the binary 
you will execute (see the corresponding Makefile) at the bottom of the SLURM script before submitting.

To build the examples make sure you have a recent version of CUDA loaded into your environment:

	$ module load CUDA

To get information about the device (i.e. GPU) try running the following from a SLURM job:

	$ /opt/easybuild/software/Core/CUDA/8.0.61/samples/1_Utilities/deviceQuery/deviceQuery

## Suggested Order

1. vector-addition
	- CPU-version  
	- Single-block-GPU-version
	- tiled-GPU-version
2. matrix-multiply
	- cpu-version
	- naive
	- tiled	 
	- shared-memory
3. multi-gpu