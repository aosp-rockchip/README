# Android for PineNote
#### What are all of these repos for?
This github organization houses all repos that were added or modified by Rockchip in the [PineNote's Android SDK](https://wiki.pine64.org/wiki/PineNote#Android_11_eink_SDK_for_PineNote_and_Quart64_model_A_SBC), as well as some of my own repos for custom builds. The `quartz64` branches have the original bsp code, only modified to make it compile. 

## Goals
The main goal of this project is to create user compilable Android builds for the PineNote, primarily focusing on improving battery life and performance. Stretch goals include a customized SystemUI and system apps to improve Android's UX on E-Ink devices. If you're interested in helping, feel free to reach out. I will update this soon with build instructions

## How to compile
I'm only providing build instructions for my customized r-11.0 branch. Ive removed a lot of unnecessary changes made in quartz64 branch, rebaserd on top of a newer android branch, and created a custom device tree. First things first, make sure you follow the android [environment setup guide](https://source.android.com/setup/build/initializing) and are familiar with the [source control tools](https://source.android.com/setup/develop). To download the sources, create a directory to hold it, cd into that and run
```
repo init -u https://github.com/aosp-rockchip/manifests -b r-11.0
```
then sync the sources
```
repo sync
```
To compile the sources, first setup your build enviromnent by running
```
source build/envsetup.sh
```
and then initialize the device
```
lunch aosp_pinenote-userdebug
```
The first time you compile the code, you'll need to build everything
```
./build.sh -UAu
```
After you flash the device with your custom fimrware the first time, you can use `./build -A` to only compile android and just flash the images with fastboot.

## How to flash the first time
By default, the pinenote comes with a vfat partition labled "device" that stores user tracking information from the stock apps. My builds don't have this partition, so the device needs to be repartitoned. This is done automatically when flashing using upgrade_tool, which you can find in `RKTools/linux/`. To flash the update image that was build ny using the `-u` flag on `build.sh`, unzip the Linux_Upgrade_Tool zip and cd into the extracted folder. By default, the upate image is stored in `/you-android-source/rockdev/Image-aosp_pinenote/`. Reboot your device into loader or maskrom mode (either works),and from the upgrade tool directory run
```
./upgrade_tool uf path/to/update.img
```
This will take a while, and your device will reboot a few times after the upgrade tool finishes to handle repartitioning and actually flashing the update.
To flash new builds after this, use fastboot to flash the super.img and boot.img located in `out/target/product/pinenote/`. This is pretty standard on android devices, so you can find a million guides for that elsewhere.
