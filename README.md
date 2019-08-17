# Potato Open Sauce Project
<img src="https://i.imgur.com/tmt6SBG.png">
Haters gonna hate, potatoes gonna potate!

Credits
-------
 * [**AOSP**](https://android.googlesource.com)
 * [**AOSiP**](https://github.com/AOSiP)
 * [**Dirty Unicorns**](https://github.com/DirtyUnicorns)
 * [**LineageOS**](https://github.com/LineageOS)

# Baked
Prepare yourself to be treated by the goodness of baked, saucy and seasoned potatoes!

### Ingredients
- Around 75G disk space
- 20G or more usable internet
- A computer with at least 8G RAM running Linux or MacOS
- A brain
- Some spices and potatoes

### Instructions
- Preparing the sauce
    1. Make sure you have a build environment setup.
    2. Make a new directory, cd to it and run
        ```
        repo init -u https://github.com/PotatoProject/manifest -b baked-release;
        repo sync;
        ```
    3. The ROM sauce is ready! Get ready to prepare your device-specific sauce.

- Preparing device sauce
    1. Define all relevant device repositories (device trees,vendor and kernel repositories) in `.repo/local_manifests/local_manifests.xml`
    2. Run `repo sync;`
    3. Move/copy your `<ROM>.mk` (Example: `lineage.mk`, `aosp_beryllium.mk`) file to `potato.mk`.
    4. Open this file and
        - Set PRODUCT_NAME to `potato_<device>` (Example: `potato_beryllium`)
        - For a Phone or tablet with a SIM Card, add
            ```
            # Inherit from Potato vendor
            $(call inherit-product, vendor/potato/config/common_full_phone.mk)
            ```
        - For a WiFi-only tablet, add
            ```
            # Inherit from Potato vendor
            $(call inherit-product, vendor/potato/config/common_full_tablet_wifionly.mk)
            ```
    5. Save and exit

- Cooking
    1. Run
        ```
        source build/envsetup.sh;
        add_lunch_combo potato_<device>-userdebug;
        brunch <device>;
        ```
        Example:
        ```
        source build/envsetup.sh;
        add_lunch_combo potato_beryllium-userdebug;
        brunch beryllium;
        ```
    2. This will start compiling the build. Keep the potato near you for luck. You may optionally eat cheese while the build compiles.
    3. Resolve errors if any and continue building.

### Reporting compilation issues
- You can reach us at [**Telegram**](https://t.me/SaucyPotatoesOfficial)
- For common porting related errors, visit [**Android Building Help**](https://t.me/AndroidBuildersHelp)
- Make sure you provide relevant logs, screenshots and details with all sources you used.

### Contributing
- You can contribute to this project by submitting changes to our [**Gerrit Code-Review**](https://review.potatoproject.co) server.

### Adding Support
- For adding your device to the list of supported devices, please reach us at [**Telegram**](https://t.me/SaucyPotatoesOfficial) with your device tree and previous works.
