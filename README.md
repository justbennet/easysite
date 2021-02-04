# EasySite

This site constitutes a journal of setting up a computing site using EasyBuild.

The basics of EasyBuild include installing software packages.  This journal
is for people who are setting up a computing _site_, which here means a computer
or set of computers configured for multiple users and managed by a person or
persons who are not typically themselves users of the software.

This journal will, we hope, provide a supplement to the EasyBuild documentation
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
do similar work.

The software that this journal uses as examples includes both serial and
parallel configurations, as we have many researchers who will never run
software that depends on MPI and who may need to compile and test software
only for single-node, multiprocessor applications.

So, we start with a serial configuration for the following software development
and support environment on which additional applications will build.  We find
that we have very few applications that do not require one or both HDF5 or
NetCDF, and use of Boost is sufficiently common that we include these in our
enhanced, base toolchains.

The intent is to provide a realistic example starting with the basic toolchains
and showing examples of increasing complexity in both a serial and parallel
environment.  For some use cases, no MPI will ever be needed.  In some others,
very few of the domain-specific packages would be needed.

### Toolchains and their components

* compiler: once for one version of GCC, once for one version of Intel
* BLAS/LAPACK (OpenBLAS, MKL)
* GSL
* Eigen
* MPICH or OpenMPI and Intel MPI
(The following have serial and MPI versions)
* Boost
* FFTW
* HDF5
* NetCDF

The following are so commonly used that we consider them part of the basic setup.
There is significant controversy over using locally maintained Python libraries
versus Anaconda, and we are hoping that we can provide a base level of locally
built Python/R libraries with EasyBuild.

* Python
  + NumPy
  + SciPy
  + Pandas
  + matplotlib

* R
  + doParallel
  + Tidyverse
  
Each of the following would be implemented as stand-alone lists that can be loaded
with a single module command.

### General image processing libraries

* libpng
* giflib
* libjpeg-turbo
* jbigkit
* tiff
* libwebp
* littlecms
* openjpeg
* jasper

### Image manipulation programs

* ImageMagick
* ffmpeg

### Genetic sequencing (bioinformatics)

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
