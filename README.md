# android_device_xiaomi_vayu
For building SHRP for Poco X3 Pro

SHRP device tree for Poco X3 Pro

The Poco X3 Pro (codenamed _"vayu"_) is a high-end smartphone from POCO

## Device specifications

| Device       | Poco X3 Pro                                 
| -----------: | :------------------------------------------ 
| SoC          | Qualcomm Snapdragon 860                     
| CPU          | Octa-core (1x2.96 GHz Kryo 485 Gold & 3x2.42 GHz Kryo 485 Gold & 4x1.78 GHz Kryo 485 Silver)
| GPU          | Adreno 640                                  
| Memory       | 6GB / 8GB  (LPDDR 4X)                       
| Shipped Android version | 11                               
| Storage      | 128GB / 256GB  (UFS 3.1)                    
| Battery      | Li-Po 5160 mAh, non-removable               
| Dimensions   | 165.3 x 76.8 x 9.4 mm                       
| Display      | 1080 x 2400 (20:9), 6.67 inches             

## Device picture

![Poco X3 Pro](https://fdn2.gsmarena.com/vv/pics/xiaomi/xiaomi-poco-x3-pro-1.jpg "Poco X3 Pro")

## Features

**Works**

- Booting.
- MTP
- OTG
- Vibration

## Compile

First checkout SHRP with aosp tree:

```
repo init -u git://github.com/SHRP/manifest.git -b v3_11.0
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

Use ccache
```
#Enable ccache
export USE_CCACHE=1
export CCACHE_EXEC=$(which ccache)
```

Finally execute these:

```
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_vayu-eng
mka recoveryimage

or

source build/envsetup.sh; lunch twrp_vayu-eng; mka recoveryimage
```

To test it:

```
/out/target/product/vayu/
```

## Thanks
- [Original Tree By Nebrassy](https://github.com/TeamWin/android_device_xiaomi_vayu)
