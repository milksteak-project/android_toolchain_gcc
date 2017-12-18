Building GCC for Android
========================

The following process is used to build the GCC that is used by both the Android
platfrom and the NDK.

Both Linux and Windows toolchains are built on Linux machines. Windows host
binaries are built with mingw. Building binaries for Mac OS X should be built
using 10.8 to ensure compatibility with Android's minimum supported hosts.

Prerequisites
-------------

* [Milksteak GCC Repository](https://github.com/milksteak-project/android_toolchain_gcc_gcc-4.9)
    * Check out the branch `milksteak-0.01a1-ndk`

      ```
      repo init -u https://github.com/milksteak-project/android_platform_manifest_gcc -b milksteak-0.01a1-ndk
      repo sync
      ```

* Additional Linux Dependencies (available from apt):
    * texinfo
    * gcc-mingw32
    * bison
    * flex
    * libtool
* Mac OS X also requires Xcode.

Host/Target prebuilts
---------------------

### For Linux or Darwin:

```bash
# Additional options and toolchain names will be show with --help.
$ python build.py --toolchain TOOLCHAIN_NAME
```

### For Windows, from Linux:

```bash
$ python build.py --system windows TOOLCHAIN_NAME
```
