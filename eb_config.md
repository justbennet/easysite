# Setting up EasyBuild itself

Count on several iterations of the configuration as you gain more
experience with EasyBuild.  There is a _lot_ to learn.

## Considerations for a site

### Root of your EasyBuild installation

We picked `/sw/arcts`, and under that there is an `easybuild` directory
in which we installed EasyBuild itself, and an `EasyBuilt` directory
in which we put all the things EasyBuild builds for us (and our config
file).

### Build location

We use `/tmp`, but we probably could use `/dev/shm/eb` as we have a
machine with 180 GB memory.  However, it is a shared machine, and
other people also use `/dev/shm` and still want to run programs.

### Setting up building within jobs

### Final installation location (NFS, CVMFS)

### Account used to build

### Cache directory(ies)

### Build node different from production (faster installation to local disk)

## Eliminate some duplication of tool-only packages

## Set up system tool chain

## Set up GNU toolchain

## Set up Intel toolchain
