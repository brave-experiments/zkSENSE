# Zokrates NDK

This project compiles ZKPs to an Android NDK library.

To use this project, please first refer to this webpage to set up the environment:

https://mozilla.github.io/firefox-browser-architecture/experiments/2017-09-21-rust-on-android.html

Android NDK can be downloaded here:

https://developer.android.com/ndk/downloads

The code to generate Zokrates NDK is in the folder `Zokrates/zokrates_android`.

To build the Zokrates NDK binary:

```bash
$ cd Zokrates/zokrates_android

# Depends on the target architecture, do one of the following three 
$ cargo build --target aarch64-linux-android --release
$ cargo build --target armv7-linux-androideabi --release
$ cargo build --target i686-linux-android --release

```