# Singularity image for Conda and Jupyter

- Step 1: Clone this repo: `git clone https://github.com/shoaibb/jupyter-singularity.git`
- Step 2: cd to the cloned repo dir: `cd jupyter-singularity`
- Step 3: Build singularity img using: `sudo singularity build jupyter.sif jupyter.def`

Now you can run jupyter notebook or jupyter lab from the built image. 

By default, the image can be used to run jupyter lab using the command: 

`./jupyter.sif`

Or if you want to specify a port, use: 

`./jupyter.sif --port=9000`

Or if you want to specify both a port and ip use: 

`./jupyter.sif --ip=1.1.1.1 --port=9000`

However, if you would like to run jupyter notebook instead of jupyter lab, use: 

`singularity exec jupyter.sif jupyter notebook --port=9000` 

You may change the port from 9000 to any other.
