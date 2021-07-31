# helloworld-android

```
export NDK_ROOT=/root/Android/Sdk/ndk/21.1.6352462

sudo ${NDK_ROOT}/toolchains/llvm/prebuilt/linux-x86_64/bin/clang \
--target=armv7-none-linux-androideabi \
--gcc-toolchain=${NDK_ROOT}/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64 \
--sysroot=${NDK_ROOT}/sysroot \
-isystem ${NDK_ROOT}/sysroot/usr/include/arm-linux-androideabi \
-o helloworld.c.o -c helloworld.c

sudo ${NDK_ROOT}/toolchains/llvm/prebuilt/linux-x86_64/bin/clang \
--target=armv7-none-linux-androideabi \
--gcc-toolchain=${NDK_ROOT}/toolchains/arm-linux-androideabi-4.9/prebuilt/linux-x86_64 \
--sysroot=${NDK_ROOT}/platforms/android-16/arch-arm/ \
-pie helloworld.c.o -o helloworld

adb push helloworld /data/local/tmp/

adb shell /data/local/tmp/helloworld
```

### REFERENCES
- https://dmerej.info/blog/post/chuck-norris-part-6-android-cross-compilation/
