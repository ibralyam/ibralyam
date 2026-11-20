# Hi, I'm ibralyam

I repack Android 15 and 16 AOSP ROMs for the Samsung Galaxy A50 (`a50dd`, Exynos 9610).
I also build custom recovery patches, flashable installers, and Xposed modules.
I study telecommunication access networks. Android is my hobby.

[![Telegram](https://img.shields.io/badge/Telegram-@ibralyam-26A5E4?logo=telegram&logoColor=white)](https://t.me/ibralyam)

## Projects

### Hybrid TWRP for Galaxy A50

[**TWRP-A50**](https://github.com/ibralyam/TWRP-A50) `3.7.1_12-0-UNOFFICIAL-@ibralyam`

A modern TWRP that still runs old TWRP v3 installers.
New TWRP builds dropped things that older zips expect. This build puts them back and keeps the new features.

**What it keeps from TWRP 3.7.1_12**

- EROFS support for system, vendor and product
- Modern decryption (Keymaster 4.x detected on boot)
- Built from the A50 `twrp-12.1` device tree
- Mint KernelSU kernel compatibility and the AVB `vbmeta.img`

**What I added**

- `/system_root` mount point, so AnyKernel3, MultiDisabler and other old installers find the system partition
- `xzcat`, `unxz` and `busybox` inside recovery, from one small static applet with a built-in LZMA decoder
  Installers no longer need to bring their own copy.
- SELinux permissive at early boot and a read-write `/tmp`
- A marker prop, `ro.ibralyam.twrp.hybrid=1`, so an installer can detect this build
- My own tag in the version string, `3.7.1_12-0-UNOFFICIAL-@ibralyam`, shown on the splash and home screen

**The installer: `twrp_flasher`**

The zip has no shell script. The installer is one static arm64 program written in C.

- Accepts only a50 and a50dd with model SM-A505. It rejects a50s and A507.
- Checks every file in the zip with CRC32 and a SHA-256 value built into the installer
- Decodes the image once before writing. It must be a valid boot image of 64 MiB or less.
- Backs up the current recovery, writes the new one, reads it back, and compares the hash
- Writes `vbmeta.img` only if the vbmeta partition exists

**Build and size**

- Built with GitHub Actions from source
- The build fails if the image is over 64 MB (67108864 bytes) or if a required tool, rc line, mount point or version string is missing
- 15 installer self tests run on every build
- The recovery image is 60.5 MiB. The zip is about 25 MB.
- The zip has no 7za and no busybox

**Install**

1. Download `TWRP_hybrid_A50.zip` from Releases
2. Boot to your current TWRP and flash it
3. Reboot to recovery

Tested on a real SM-A505F. Details, limits and the full build guide are in the repository.

### Flashable ROM zips

Each ROM comes as an all-in-one TWRP flashable zip that installs in this order:

1. Vendor
2. MultiDisabler
3. GSI system
4. Mint KernelSU kernel
5. KernelSU Manager (optional)
6. System Resizer
7. BiTGApps (only on vanilla builds)

The installer prints progress and checks every image before it writes.

ROMs: RisingOS, RestlessOS, LineageOS, AxionOS, crDroid, InfinityX, PixelOS, DerpFest, Sakura, Clover, Evolution X, and AlphaDroid.

Downloads are on the Releases page of each repository.

### Xposed and LSPosed modules

[**StatusBar Hider**](https://github.com/ibralyam/statusbar-hider)
Hides the status bar per app on Android 12 to 16. It helps reduce OLED burn-in.
The bar shows briefly when you swipe from the top edge.

## Known issues on A50 AOSP ROMs

These do not work on AOSP ROMs for this phone:

- Fingerprint (FOD)
- Vibration
- Ultrawide camera
- Macro camera

## Contact

Telegram: [t.me/ibralyam](https://t.me/ibralyam)
