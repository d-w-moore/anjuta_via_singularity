# Anjuta IDE via Singularity

The container includes libraries for building and debugging  C++
programs with GCC 9, with C++17 support and Boost libraries. C/Xlib
applications are also supported.

To build the container under Singularity ~2.5.1 :

  - get [Singularity](http://sylabs.io) . If you're on Ubuntu/Debian,
   the [NeuroDebian](https://neuro.debian.net) repo can offer the
   most up-to-date Singularity packages
  - in a local copy of this repo, use the build command:
  ```
  $ sudo singularity build anjuta.simg Singularity
  ```
  - The IDE can be lauched by running anjuta.simg as an executable
  ```
  $ ./anjuta.simg
  ```
  or via the singularity application
  ```
  $ singularity run anjuta.simg
  ```

To alter an existing image:

```
$ sudo singularity build --sandbox anjuta anjuta.simg
$ sudo singularity shell --writable anjuta
Singularity> apt update; apt install {custom-packages...}
Singularity> exit
$ sudo build anjuta_updated.simg anjuta
```
