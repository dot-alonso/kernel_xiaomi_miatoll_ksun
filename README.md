# Evolution X Miatoll Kernel with KernelSU Next

KernelSU Next Intergation for Evolution X Android 16 Kernel on Xiaomi Miatoll Devices.

## Device

* Redmi Note 9 Pro
* Redmi Note 9S
* Redmi Note 9 Pro Max
* POCO M2 Pro

## Base

**Source:**
https://github.com/Evolution-X-Miatoll/android_kernel_xiaomi_sm6250

**Kernel:**
Linux 4.14.356-openela-rc1

**Android:**
Evolution X 11.4.1 - Android 16

**KernelSU Next:**
`3.2.0` integrated **in legacy mode using manual hooks**.

## Building

```
make O=out ARCH=arm64 vendor/xiaomi/miatoll_defconfig

make -j$(nproc) O=out ARCH=arm64 \
  CC=clang \
  LD=ld.lld \
  AR=llvm-ar \
  NM=llvm-nm \
  OBJCOPY=llvm-objcopy \
  OBJDUMP=llvm-objdump \
  STRIP=llvm-strip \
  CROSS_COMPILE=aarch64-linux-gnu- \
  CROSS_COMPILE_ARM32=arm-linux-gnueabi- \
  CROSS_COMPILE_COMPAT=arm-linux-gnueabi-
```

## Notes

This kernel is intended only for the Evolution X `11.4.1` Android 16 build it was compiled against.

Using it with other ROMs or different Evolution X releases may result in boot failure.
