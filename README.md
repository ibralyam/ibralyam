# Hi, I'm ibralyam

I port and repack Android 15 and 16 AOSP ROMs for the Samsung Galaxy A50 (`a50dd`, Exynos 9610).
I also build custom recovery patches, flashable installers, and Xposed modules.
I study telecommunication access networks. Android is my hobby.

[![Telegram](https://img.shields.io/badge/Telegram-@ibralyam-26A5E4?logo=telegram&logoColor=white)](https://t.me/ibralyam)

## Projects

### Hybrid TWRP for Galaxy A50

[**TWRP-A50**](https://github.com/ibralyam/TWRP-A50) `3.7.1_12-0-UNOFFICIAL-@ibralyam`

TWRP 3.7.1_12 that also works with old TWRP v3 installers.

- Adds `/system_root`, `xzcat`, `unxz` and `busybox` to recovery
- Permissive SELinux and a read-write `/tmp`
- Static C installer, `twrp_flasher`
  - Checks the device model
  - Checks every file with CRC32 and SHA-256
  - Verifies the write by reading it back
- Built with GitHub Actions, and the build fails above 64 MB
- Zip under 30 MB

### Flashable ROM zips

Each ROM comes as an all-in-one TWRP flashable zip that installs in this order:

1. Vendor
2. MultiDisabler
3. GSI system
4. Mint KernelSU kernel
5. System Resizer
6. BiTGApps (only on vanilla builds)

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
