# Android for PineNote
#### What are all of these repos for?
This github organization houses all repos that were added or modified by Rockchip in the [PineNote's Android SDK](https://wiki.pine64.org/wiki/PineNote#Android_11_eink_SDK_for_PineNote_and_Quart64_model_A_SBC), as well as some of my own repos for custom builds. The `quartz64` branches have the original bsp code, only modified to make it compile. 

## Goals
The main goal of this project is to create user compilable Android builds for the PineNote, primarily focusing on improving battery life and performance. Stretch goals include a customized SystemUI and system apps to improve Android's UX on E-Ink devices. If you're interested in helping, feel free to reach out. I will update this soon with build instructions


## Abandoned this idea for now
To get the current sources for PineNote with LineageOS, place the lineage.xml file from this repo into `<your lineage source>/.repo/local_manifests/` and run a `repo sync` command. To build LineageOS for the device, run `source build/envsetup.sh && lunch lineage_pinenote-userdebug && mka` from the root of your Lineage source tree. Note that the work I'm doing is specifically for LineageOS 19.1 (Android 12L) which is still considered to be "in development".
