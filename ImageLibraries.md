# Installing the image library collection

I began installing the collection of image libraries that we wanted based on
having installed `GCCcore/8.3.0`, which provided the following list of available
modules

```
   Bison/3.0.4          M4/1.4.17            flex/2.6.4         settarg
   Bison/3.3.2   (D)    M4/1.4.18     (D)    help2man/1.47.4    zlib/1.2.11
   GCCcore/8.3.0        binutils/2.32        lmod
```

where the `lmod` and `settarg` modules are from the Lmod `Core` modules.

The list of libraries from our previous installations that we wanted to include
in our collection of image libraries follows.

```
libpng         giflib         libjpeg-turbo
jbigkit        tiff           libwebp
littlecms      openjpeg       jasper
ImageMagick    ffmpeg
```

To see what was available, I used
```
$ for pkg in libpng giflib libjpeg-turbo jbigkit tiff libwebp \
      littlecms openjpeg jasper ImageMagick ffmpeg ; do
      echo Looking for $pkg
      eb --search $pkg | grep GCCcore-8.[23]
done

Looking for libpng
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libpng/libpng-1.6.36-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libpng/libpng-1.6.37-GCCcore-8.3.0.eb
Looking for giflib
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/g/giflib/giflib-5.1.4-GCCcore-8.2.0.eb
Looking for libjpeg-turbo
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libjpeg-turbo/libjpeg-turbo-2.0.2-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libjpeg-turbo/libjpeg-turbo-2.0.3-GCCcore-8.3.0.eb
Looking for jbigkit
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/j/jbigkit/jbigkit-2.1-GCCcore-8.2.0.eb
Looking for tiff
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/LibTIFF/LibTIFF-4.0.10-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/LibTIFF/LibTIFF-4.0.10-GCCcore-8.3.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/LibTIFF/LibTIFF-4.1.0-GCCcore-8.3.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libgeotiff/libgeotiff-1.5.1-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libgeotiff/libgeotiff-1.5.1-GCCcore-8.3.0.eb
Looking for libwebp
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/libwebp/libwebp-1.0.2-GCCcore-8.2.0.eb
Looking for littlecms
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/LittleCMS/LittleCMS-2.9-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/l/LittleCMS/LittleCMS-2.9-GCCcore-8.3.0.eb
Looking for openjpeg
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/o/OpenJPEG/OpenJPEG-2.3.1-GCCcore-8.2.0.eb
Looking for jasper
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/j/JasPer/JasPer-1.900.1-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/j/JasPer/JasPer-2.0.14-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/j/JasPer/JasPer-2.0.14-GCCcore-8.3.0.eb
Looking for ImageMagick
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/i/ImageMagick/ImageMagick-7.0.8-46-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/i/ImageMagick/ImageMagick-7.0.9-5-GCCcore-8.3.0.eb
Looking for ffmpeg
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/f/FFmpeg/FFmpeg-4.1.3-GCCcore-8.2.0.eb
 * /sw/arcts/centos7/easybuild/software/EasyBuild/4.1.1/easybuild/easyconfigs/f/FFmpeg/FFmpeg-4.2.1-GCCcore-8.3.0.eb
```
