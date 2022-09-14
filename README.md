# Singularity image for Conda and Jupyter

This repo can be used to create a Singularity image for miniconda (with python 3.9) and jupyter lab. The image file can be used to run jupyter lab with some packages that are specified in the `requirements.txt` file. The jupyter lab will write to /tmp location inside the container and it is suggested to bind a local dir to /tmp. The created image file will be approx. 900MB in size.

### Steps to build the image:

- Step 1: Clone this repo: `git clone https://github.com/shoaibb/jupyter-singularity.git`
- Step 2: cd to the cloned repo dir: `cd jupyter-singularity`
- Step 3: Build singularity img using: `sudo singularity build /path/to/img-dir/jupyter.sif jupyter.def`

IMPORTANT: make sure you change **/path/to/img-dir** to a location that exists on your system as it will be the final destination of the built image file **jupyter.sif**.  

### Running jupyter from the image file:

You can run jupyter notebook or jupyter lab from the built image. First of all, cd to the path where the image file is created (same path as spcified in Step 3 above). 
By default, the image can be used to run jupyter lab using the command: 

`singularity run --bind /path/to/data:/tmp jupyter.sif`

Or if you want to specify a port, use: 

`singularity run --bind /path/to/data:/tmp jupyter.sif --port=9000`

Or if you want to specify both a port and ip use: 

`singularity run --bind /path/to/data:/tmp jupyter.sif --ip=1.1.1.1 --port=9000`

You may change the port from 9000 to any other.
