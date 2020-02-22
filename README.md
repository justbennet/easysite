# EasySite

This site constitutes a tutorial for setting up a computing site using EasyBuild.

The basics of EasyBuild include installing software packages.  This tutorial
is for people who are setting up a computing _site_, which here means a computer
or set of computers configured for multiple users and managed by a person or
persons who are not typically themselves users of the software.

This tutorial will, we hope, provide a supplement to the EasyBuild documentation
that will enable a site administrator to

* install EasyBuild
* configure EasyBuild to use a central software repository
* install toolchains for both serial and parallel software building
  using both an open source and a commercial compiler
* create the necessary files to support replication of the site configuration,
  including installation of all toolchains and applications easily.

We will here call that a _site specification_, to distinguish it from the
site configuration that tells EasyBuild about its options.  We have included
several sets of software that we have recently had to install to support
particular research projects/scientific domains.  These are here for our
benefit and as a gallery of examples for others.

The motivating environment for this is a university where we have multiple
administrative units each of which may provide a computer or computers to
do similar work.  So, for example, the site configuration might be deployed
on three independent computers in a research lab that use it to install
everything to their local disks, or it might be used on three compute
each of which has its own shared NFS software installation but have nothing
in common among them.

The software that this tutorial uses as examples includes both serial and
parallel configurations, as we have many researchers who will never run
software that depends on MPI and who may need to compile and test software
only for single-node, multiprocessor applications.

So, we start with a serial configuration for the following software development
and support environment on which additional applications will build.  We find
that we have very few applications that do not require one or both HDF5 or
NetCDF, and use of Boost is sufficiently common that we include these in our
enhanced, base toolchains.

The base toolchain would also be created for two MPI flavors:  OpenMPI 4.0.2
and Intel MPI 2019.6.166 (from the Intel 2020.0 cluster studio release).  HDF5
will need both the 1.8 and 1.10 versions.  That has implications for how many
NetCDF configurations and of which type.  Boost has a dependency on Python, so
at the time of writing needs to support Python 2 and 3.

The intent is to provide a realistic example starting with the basic toolchains
and showing examples of increasing complexity in both a serial and parallel
environment.  For some use cases, no MPI will ever be needed.  In some others,
very few of the domain-specific packages would be needed.

**Toolchain components**

* compiler
* BLAS/LAPACK (OpenBLAS, MKL)
* Boost
* Eigen
* HDF5
* NetCDF

The following are so commonly used that we consider them part of the basic setup.
There is significant controversy over using locally maintained Python libraries
versus Anaconda, and we are hoping that we can provide a base level of locally
build Python/R libraries with EasyBuild.

* Matlab

* Python
  + NumPy
  + SciPy
  + Pandas

* R
  + doParallel
  + Tidyverse
  
Each of the following would be implemented as stand-alone lists that can be installed
with a single command.

**General image processing libraries**

* libpng
* giflib
* libjpeg-turbo
* jbigkit
* tiff
* libwebp
* littlecms
* openjpeg
* jasper
* ImageMagick
* ffmpeg

**Geospatial statistics**

* R
  + inconsolata
  + texlive
  + knitr
  + rstan
  + Geospatial libraries (optional)
  + Rmpi

**Neuroimaging analysis**

* Matlab
  + SPM12
  + marsbar
  + EEGlab
* FSL (GPU support for bedpostx_gpu, eddy_cuda, probtrackx2_gpu, split_parts_gpu, xfibres_gpu)
* AFNI
* FreeSurfer
* ANTs
* FMRIPREP (container)
* MRtrix3
* VTK
* ITK
* Eigen

**Genetic sequencing (bioinformatics)**

* samtools
* subread
* star
* fastqc
* cufflinks
* salmon
* bwa
* bowtie2
* picard
* vcftools
