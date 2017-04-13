# MIRTK Singularity image

A bootstrap definition for a [Singularity](http://singularity.lbl.gov/) image based on the [Medical Image Registration ToolKit (MIRTK)](https://github.com/BioMedIA/MIRTK) docker image.

## Creating the image _requires root_:

See [Singularity](http://singularity.lbl.gov/) documentation for more information.

1. Create an empty container

`sudo singularity create MIRTK.img`

2. Bootstrap the container 

`sudo singularity bootstrap MIRTK.img Singularity.def`


## Usage

The container is basically a complete environment with the MIRTK toolkit installed.

To obtain shell access to the container

`singularity shell MIRTK.img`

Two mountpoints are provided:
`/input`
`/output`

These can be used to interact with the local filesystem using the `-B` option.

To convert a pointset from one format to another:

`singularity run -B <src_dir>:/input -B <dst_dir>:/output MIRTK.img convert-pointset /input/<input_file> /output/<output_file>`
