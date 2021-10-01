<h3 align="center"><img src="https://github.com/SukeeratSG/dump-public/blob/iron/Assets/havoc_favicon.svg" width="30%" height="30%"></h3>
<h3  align="center">This is a guide for how to build Havoc-OS</h3>

If you don't want to build and just get the release builds for your device ( [Download](https://havoc-os.com/download) )


Getting Started
---------------
To get started with the Havoc-OS sources, you'll need to get
familiar with [Git and Repo](https://source.android.com/setup/develop).

Setup
----------------------

You will need to set up some directories in your build environment.

To create them run:

```bash
   mkdir -p ~/bin
   mkdir -p ~/havoc
```

Enter the following to download the "repo" binary and make it executable:

```
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
PATH=~/bin:$PATH
```

You may need to reboot for these changes to take effect.
Now enter the following to initialize the repository:

```bash
   cd ~/havoc
```

```bash
   repo init -u https://github.com/Havoc-OS/android_manifest.git -b eleven
```
Or if you are short on space  

```bash
   repo init -u https://github.com/Havoc-OS/android_manifest.git -b eleven --depth=1
```

This syncs everything in background.

```bash
  repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags -q
```

Building the System
---------------

Please note that if you are building on Mac OS X, you are required to install coreutils from MacPorts before you continue.

Initialize the environment with the envsetup.sh script. Note that replacing "source" with a single dot saves a few characters, and the short form is more commonly used in documentation.

```bash
   . build/envsetup.sh
    brunch
```

Enter the number of the build you want to start and press enter or brunch device_name to build it directly


# Preparing Havoc-OS for your devices

You can always check out our [**device organization**](https://github.com/havoc-Devices) for reference.
And we release bi-weekly so if your device is actively maintaned , you never need to come here.
Check out our actively minatined devices (here)(https://havoc-os.com/download)

If your device supports cellular data, then set this in havoc_device.mk:

>>        # Inherit some common havoc stuff.
>>        $(call inherit-product, vendor/havoc/config/common_full_phone.mk)

If it doesn't, then set this in havoc_device.mk:

>>        # Inherit some common havoc stuff.   
>>        $(call inherit-product, vendor/havoc/config/common.mk)

# Google Based apps

After lunching your build, you can do this to build Google Based apps with the ROM

>>        export WITH_GAPPS=true

or add this on your havoc_device.mk:

>>  WITH_GAPPS := true

Moreover havoc comes with google's roomservice which allows you just sync and build without any effort.