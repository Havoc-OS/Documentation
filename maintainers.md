<h3 align="center"><img src="https://github.com/SukeeratSG/dump-public/blob/iron/Assets/havoc_favicon.svg" width="30%" height="30%"></h3>
<h3  align="center">This is a guide for how to build the official verision of HavocOS</h3>

### Guide for maintainers

- First step is to check  [the official devices repository](https://github.com/Havoc-Os/official_devices).
- Update your details in the both the files as the CI pulls which devices to build from this [file](https://github.com/Havoc-OS/official_devices/blob/eleven/devices) 
- While it pulls posting details from this [file](https://github.com/Havoc-OS/official_devices/blob/eleven/README.md)
- The manifest being tracked in ci builds is publically available [here](https://github.com/SukeeratSG/android_manifest)
- Required props are for official maintainers : 

> ro.havoc.device.name=Poco F3  <br>
> ro.havoc.group.url=https://t.me/havocalioth_in <br> 
> ro.havoc.maintainer=Sukeerat Singh Goindi <br>
> ro.havoc.maintainer.username=irongfly <br>

Please add these props in your device repos.

*1st line: Device name  <br> 
2nd line: Telegram device group link <br>
3rd line: Your full name <br>
4th line: Your telegram username* <br>

- To push an over the air update for havoc-os (OTA) , you need to update  [this](https://github.com/Havoc-OS/OTA) repo is needed
- To add an changelog like  [this](https://raw.githubusercontent.com/Havoc-OS/OTA/eleven/vanilla/alioth_1628134829.json) can be added with generated buildtime
- After that push your device trees with the naming scheme like **android_XXX** and with branch eleven
- For example for alioth we need device-common , vendor , vendor common and the kernel
So that it becomes 

> Kernel -
> [android_kernel_xiaomi_alioth](https://github.com/Havoc-Devices/android_kernel_xiaomi_alioth)
> <br> DT - 
> [android_device_xiaomi_alioth](https://github.com/Havoc-Devices/android_device_xiaomi_alioth)
> <br>  DT Common -
> [android_device_xiaomi_alioth-common](https://github.com/Havoc-Devices/android_device_xiaomi_alioth-common)
> <br>  Vendor Common  - 
> [android_vendor_xiaomi_alioth-common](https://github.com/Havoc-Devices/android_vendor_xiaomi_alioth-common)
> <br>

- Now for dependencies , they should all be on Havoc-Devices  (An [example](https://github.com/Havoc-Devices/android_device_xiaomi_alioth/blob/eleven/havoc.dependencies) )
- Note :- If you add a directory to be synced which already exists , please use vendor/ci/codename.sh (For Examples [hals](https://github.com/Havoc-Devices/android_vendor_ci/blob/main/alioth.sh))
- Now for patches or source changes you might need you can push to [Code Review System](https://review.havoc-os.com) and cherry-pick in the same file.
- For an guide on our code review process visit [here](https://github.com/Havoc-Devices/android_device_xiaomi_alioth/blob/eleven/havoc/review.md)
- For user builds , export buildtype="user" in [ci repo.sh](https://github.com/Havoc-Devices/android_vendor_ci/blob/eleven/alioth.sh#L19)