# Hi, I'm ibralyam

I repack Android 15–16 AOSP ROMs for the Samsung Galaxy A50 (`a50dd`, Exynos 9610), build custom recovery patches and installers, and make Xposed/LSPosed modules.

## ROMs & Recovery

- **Hybrid TWRP (`3.7.1_12-0-UNOFFICIAL-@ibralyam`):** TWRP 3.7.1_12 for Galaxy A50 with `/system_root`, `xzcat`/`unxz`/`busybox` + `/sbin/sh`, permissive SELinux, static C `twrp_flasher` with CRC32/SHA-256 checks & write verification, built via GitHub Actions CI
- **Flashable TWRP zips:** Vendor, MultiDisabler, GSI, Mint KernelSU kernel, System Resizer, and custom Hybrid TWRP
- **Supported ROMs:** RisingOS, RestlessOS, LineageOS, AxionOS, crDroid, InfinityX, PixelOS, DerpFest, Sakura
- **Extras:** Optional BiTGApps for vanilla builds, shell installer scripts with checks and progress output
- **Downloads:** See Releases in each repository
- **Known issues (A50 AOSP):** FOD, Vibration, Ultrawide, and Macro do not work on AOSP ROMs for this phone

## Xposed / LSPosed Modules

- **[StatusBar Hider](https://github.com/ibralyam/statusbar-hider):** Hides the status bar per app on Android 12–16 to help reduce OLED burn-in, showing it only briefly on top-edge swipe

## Contact

Telegram: [t.me/ibralyam](https://t.me/ibralyam)
