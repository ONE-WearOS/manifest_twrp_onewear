## Getting Started ##
---------------

To get started with OMNI sources to build TWRP, you'll need to get
familiar with [Git and Repo](https://source.android.com/source/using-repo.html).

To initialize your local repository using the OMNIROM trees to build TWRP, use a command like this:

    repo init -u https://github.com/ONE-WearOS/manifest_twrp_onewear.git -b twrp-9.0

To initialize a shallow clone, which will save even more space, use a command like this:

    repo init --depth=1 -u https://github.com/ONE-WearOS/manifest_twrp_onewear.git -b twrp-9.0

Then to sync up:

    repo sync
    
## Python Requirement Note ##
-----------------------

Before building, make sure you have your system's python implementation set to python2. 
This project was created before python2 was deprecated and will not build with python3.

## Build ##
-----

Then to build for a device with recovery partition:

     cd <source-dir>; export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch omni_<device>-eng; mka recoveryimage

Then to build for a device without recovery partition:

     cd <source-dir>; export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch omni_<device>-eng; mka bootimage
