# aosp-rockchip
This organization consists of git repos for android on the Pine64 Quartz64, pulled from the BSP. Currently, the main focus of this effort is to build custom roms for the PineNote. Work is being done to restructure these repos into a more suitable form for AOSP/LineageOS

To get the current sources for PineNote with LineageOS, place the lineage.xml file from this repo into `<your lineage source>/.repo/local_manifests/` and run a `repo sync` command. To build LineageOS for the device, run `source build/envsetup.sh && lunch lineage_pinenote-userdebug && mka` from the root of your Lineage source tree. Note that the work I'm doing is specifically for LineageOS 19.1 (Android 12L) which is still considered to be "in development".
