# Android for PineNote
#### Disecting the QUARTZ64 model A E-Ink Android 11 SDK and making it more useful
This github organization houses all repos that were added or modified by Rockchip in the [PineNote's Android SDK](https://wiki.pine64.org/wiki/PineNote#Android_11_eink_SDK_for_PineNote_and_Quart64_model_A_SBC). The two exceptions to this are [android_PATCHES](https://github.com/aosp-rockchip/android_PATCHES), which houses all of the changes Rockchip made to AOSP in patch form, and [android_device_pine64_pinenote](https://github.com/aosp-rockchip/android_device_pine64_pinenote), which is a device tree specifically for the PineNote, and this repo. If you're interested in helping, please reach out!

## Goals
The main goal of this project is to breakout the unique components from the SDK and maintain them so that Android support can continue beyond the provided Android 11 Febuary 2021 release provided by Rockchip. Support is also being added for use in custom forks of Android like CarbonROM and LineageOS. Stretch goals include a customized SystemUI and system apps to improve Android's UX on E-Ink devices. Again, if you're interested in helping, please reach out!

## Techincal info
To get the current sources for PineNote with LineageOS, place the lineage.xml file from this repo into `<your lineage source>/.repo/local_manifests/` and run a `repo sync` command. To build LineageOS for the device, run `source build/envsetup.sh && lunch lineage_pinenote-userdebug && mka` from the root of your Lineage source tree. Note that the work I'm doing is specifically for LineageOS 19.1 (Android 12L) which is still considered to be "in development".
