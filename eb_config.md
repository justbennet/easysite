# Setting up EasyBuild itself

## Considerations for a site

What is the root of your EasyBuild installation?

Build location

Setting up building within jobs?

Final installation location (NFS, CVMFS)

Account used to build

Cache directory(ies)

Build node different from production (faster installation to local disk)

## Eliminate some duplication of tool-only packages

In particular M4, Bison, Flex, et al.  Should only need one of these per toolchain.
Would it make sense to have a versioned build-tools that gets added as a layer
below the current toolchain and on which everything else depends?  That would
reduce the duplications induced by hard numbering of dependencies?

## Set up system tool chain

## Set up GNU toolchain

## Set up Intel toolchain
