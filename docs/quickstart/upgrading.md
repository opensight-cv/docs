Depending on which version of OpenSight you are using, you may or may not be able to use the upgrader. If you installed using the [Raspberry Pi image](installation.md#installing-on-raspberry-pi) or the [Debian ARM systems (packages) method](installation.md#installing-on-debian-arm-systems) you are able to use the upgrader.

![Image of the updater in settings](/assets/images/update.png)

The current version number is viewable in the bottom left of the settings page.

## Upgrading on Raspberry Pi

If you are on Raspberry Pi, you can do the following to update your OpenSight installation:

1. Download the **with dependencies tar.gz file** on the [latest release page](https://github.com/opensight-cv/packages/releases/latest) from the packages repository.
2. Go to the settings page OpenSight instance.
3. Drag and drop the file into the "Update" box, or browse and select the file.
4. Click the "Update" button. 
5. Your Raspberry Pi should now start updating. This may take multiple minutes. Once you are able to access OpenSight again, updating should be finished.
    * If OpenSight is not accessible after approximately 10 minutes, either reflash the image or join [our Discord](https://discord.gg/hPqpdsK) for support.

!!! info
    **Technical Implications**: The with dependencies tar.gz file contains updates for system packages as well the OpenSight packages. This ensures that any dependencies of OpenSight are upgraded along with OpenSight, and no manual upgrading is required.

## Upgrading on other Debian systems

If you are on a different ARM Debian system, you can do the following to update your OpenSight installation:

1. Download the **normal tar.gz file** (eg. not the with-dependencies file) on the [latest release page](https://github.com/opensight-cv/packages/releases/latest) from the packages repository.
2. Go to the settings page OpenSight instance.
3. Drag and drop the file into the "Update" box, or browse and select the file.
4. Click the "Update" button. 
    * If OpenSight is not accessible after approximately 10 minutes, either reinstall OpenSight manually or join [our Discord](https://discord.gg/hPqpdsK) for support.
