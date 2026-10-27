# ath9k_htc module for Xiaomi Mi 9T / Redmi K20 (davinci)

Builds `ath9k_htc.ko` (+ `mac80211.ko`, `ath9k_hw.ko`, `ath9k_common.ko`) as
loadable modules for **LineageOS 23.2-20261004-NIGHTLY-davinci** (Android 16,
kernel `4.14.357-openela-perf-ge03e5ba22586`), to be installed via `insmod`
without reflashing boot.img.

Target USB adapter: Atheros AR9271, USB ID `0cf3:9271`.

## Provenance
- Kernel source: https://github.com/LineageOS/android_kernel_xiaomi_sm6150
  branch `lineage-23.2`, pinned commit `e03e5ba22586` (HEAD at ROM build date).
- Defconfig: `vendor/sdmsteppe-perf_defconfig` + `vendor/davinci.config`
  (same merge order as LineageOS kernel.mk).
- Toolchain: Android clang 21.0.0 (`r563880c`) from AOSP prebuilts
  (tag `android-16.0.0_r4`), binutils = distro `aarch64-linux-gnu-`.
- Config fragments: `ath9k_htc.config` (this repo).

Expected vermagic of the built modules:
`4.14.357-openela-perf-ge03e5ba22586 SMP preempt mod_unload modversions aarch64`

## Firmware
ath9k_htc needs `htc_9271-1.4.0.fw` (shipped separately in output/).
