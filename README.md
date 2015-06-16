
# OPENJPEG Library and Applications

## Details on folders hierarchy

* src
  * lib
    * openjp2: contains the sources of the openjp2 library (Part 1 & 2)
    * openjpwl: contains the additional sources if you want to build a JPWL-flavoured library.
    * openjpip: complete client-server architecture for remote browsing of jpeg 2000 images.
    * openjp3d: JP3D implementation
    * openmj2: MJ2 implementation
  * bin: contains all applications that use the openjpeg library
    * common: common files to all applications
    * jp2: a basic codec
    * mj2: motion jpeg 2000 executables
    * jpip: OpenJPIP applications (server and dec server)
      * java: a Java client viewer for JPIP
    * jp3d: JP3D applications
      * tcltk: a test tool for JP3D
    * wx
      * OPJViewer: gui for displaying j2k files (based on wxWidget)
* wrapping
  * java: java jni to use openjpeg in a java program
* thirdparty: thirdparty libraries used by some applications. These libraries will be built only if there are not found on the system. Note that libopenjpeg itself does not have any dependency.
* doc: doxygen documentation setup file and man pages
* tests: configuration files and utilities for the openjpeg test suite. All test images are located in 'http://openjpeg.googlecode.com/svn/data' folder.
* cmake: cmake related files

See [LICENSE](https://github.com/uclouvain/openjpeg/blob/master/LICENSE) for license and copyright information.

See [INSTALL](https://github.com/uclouvain/openjpeg/blob/master/INSTALL) for installation procedures.

See [NEWS](https://github.com/uclouvain/openjpeg/blob/master/NEWS) for user visible changes in successive releases.

## API/ABI

OpenJPEG strives to provide a stable API/ABI for your applications. As such it
only exposes a limited subset of its functions.  It uses a mechanism of
exporting/hiding functions. If you are unsure which functions you can use in
your applications, you should compile OpenJPEG using something similar to gcc:
`fvisibility=hidden` compilation flag.
See also: http://gcc.gnu.org/wiki/Visibility

On windows, MSVC directly supports export/hiding function and as such the only
API available is the one supported by OpenJPEG.
