# Installing the image library collection

Basing things on GCCcore/GCC 9.3.0 now.

The list of libraries from our previous installations that we wanted to include
in our collection of image libraries follows.

```
libpng         giflib         libjpeg-turbo
jbigkit        tiff           libwebp
littlecms      openjpeg       jasper
```

In addition, we would like to have the programs `ImageMagick` and `ffmpeg`,
but those should probably not be in the library collection.

To see what was available, I used

```
$ for pkg in libpng giflib libjpeg-turbo jbigkit tiff libwebp \
      littlecms openjpeg jasper ; do
      echo Looking for $pkg
      eb --search $pkg | egrep 'GCCcore-9.3|GCC-9.3'
done
Looking for libpng
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/l/libpng/libpng-1.6.37-GCCcore-9.3.0.eb
Looking for giflib
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/g/giflib/giflib-5.2.1-GCCcore-9.3.0.eb
Looking for libjpeg-turbo
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/l/libjpeg-turbo/libjpeg-turbo-2.0.4-GCCcore-9.3.0.eb
Looking for jbigkit
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/j/jbigkit/jbigkit-2.1-GCCcore-9.3.0.eb
Looking for tiff
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/l/LibTIFF/LibTIFF-4.1.0-GCCcore-9.3.0.eb
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/l/libgeotiff/libgeotiff-1.5.1-GCCcore-9.3.0.eb
Looking for libwebp
Looking for littlecms
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/l/LittleCMS/LittleCMS-2.9-GCCcore-9.3.0.eb
Looking for openjpeg
Looking for jasper
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/j/JasPer/JasPer-2.0.14-GCCcore-9.3.0.eb
 * /sw/arcts/easybuild/software/EasyBuild/4.3.2/easybuild/easyconfigs/j/JasPer/JasPer-2.0.16-GCCcore-9.3.0.eb
```
There was (at time of writing) an easyconfig for
`OpenJPEG/OpenJPEG-2.3.1-GCCcore-8.3.0.eb` and for
`libwebp-1.1.0-GCCcore-8.3.0.eb`, so those should be easily
updated to `GCCcore-9.3.0`.

Also found `FFmpeg-4.2.2-GCCcore-9.3.0.eb` and
`ImageMagick-7.0.9-5-GCCcore-8.3.0.eb`.

The easyconfig for FFmpeg installs X windows and many other dependencies.

ImageMagick has a huge trail of dependencies that need updating for
GCCcore-9.3.0.
