# android-sysinfo

## Overview

`android-sysinfo` is a Android Native program which reports the system
properties of any android device using the [system properties][1] [C API][2]
existing in Android libc [bionic][3].

It is simlar to the `Settings or System > About the Phone` system information
displayed on your mobile device.

It reports the model, build version and kernel info, etc.

## Requirements

You need to install the Android SDK and Android NDK to use `adb` and `ndk-build`
used in the build process.

## Build

The build Makefile is using [adb][4] to determine the Android version and ABI of
the NDK to use in order to produce the binary.

Connect your Android device via USB and enable USB Debugging, then run:

```
make push
```

## Run

```
make run
```

## Output on devices

On few of my personal Android devices, this is what output information look likes.

### Nexus S

[Nexus S](https://en.wikipedia.org/wiki/Nexus_S)

```
Model number             : Nexus S
Android codename         : crespo
Android version          : 4.1.2
Android SDK version      : 16
Kernel version           : Linux 3.0.31-g5894150 android-build@vpba17.mtv.corp.google.com #1 PREEMPT Mon Sep 10 14:10:13 PDT 2012 armv7l
Baseband version         : I9023XXKI1
Build number             : JZO54K
```

### Huawei P20

[Huawei P20 Pro](https://en.wikipedia.org/wiki/Huawei_P20)

```
Model number             : CLT-L09
Android codename         : CLT
Android version          : 9
Android SDK version      : 28
Kernel version           : Linux 4.9.148 test@cn-central-1b-e859467521576132696835-1535427282-tvxt6 #1 SMP PREEMPT Thu Dec 12 15:34:28 CST 2019 aarch64
Baseband version         : 21C20B369S009C000
Build number             : CLT-L09 9.1.0.372(C782E12R1P11)
```

[1]: https://android.googlesource.com/platform/bionic/+/master/libc/include/sys/system_properties.h
[2]: https://developer.android.com/ndk/guides/stable_apis#c_library
[3]: https://android.googlesource.com/platform/bionic/
[4]: https://developer.android.com/studio/command-line/adb
