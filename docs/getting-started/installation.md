## Installing on Raspberry Pi

!!! note
    This is only required on the first installation of the image. After that, you can use the [upgrader](upgrading.md) in order to upgrade your installation. Any exceptions to this will be plainly noted on the releases page.

* Insert your Raspberry Pi's Micro SD card into your computer. Please note that you need a Micro SD card with at least 4GB. **All data on the SD card will be erased during the installation process**.
* Download the latest Raspberry Pi image file [from the releases page](https://github.com/opensight-cv/opsi-gen/releases/latest). 
* Install a disk imaging software. The simplest imaging software is [balenaEtcher](https://www.balena.io/etcher/).
* Click "Select an Image" and select the .zip file image you downloaded in step 1.
* For the drive, select your Micro SD card.
* Click "Flash".

After this finishes, you can put your Micro SD card back into your Pi. OpenSight should now be running! Continue to the [Quick Start](quickstart.md) page.

If you have any issues, please join our [Discord](https://discord.gg/hPqpdsK), let us know the issue in the #help channel and we'll help you troubleshoot.

## Installing on Debian ARM systems

If you are running a Debian ARM based system, you can use the same packages generated for the Raspberry Pi. If the output of `dpkg-architecture -q DEB_BUILD_ARCH` is `armhf`, you can use the following set of instructions. Types of systems that meet this requirement would be:

* Raspberry Pi
* Jetson Nano
* Many coprocessors

Here are the differences between using the packages and installing with the regular Linux script:

* Automatic startup
* Installed system-wide
* Can use the [upgrader](upgrading.md)

Run these commands to do so:
```bash
sudo apt update
sudo apt install -y curl git jq
mkdir /tmp/opsi; cd /tmp/opsi
url="$(curl https://api.github.com/repos/opensight-cv/packages/releases/latest | jq -r '.["assets"][]["browser_download_url"]' | grep -v with)"
curl -LO $url
mkdir -p packages
tar xf opsi-packages-*.tar.gz -C packages
sudo apt install -y ./packages/deps/*.deb
rm -rf /tmp/opsi/
```

## Installing on other systems

Currently, OpenSight is only directly supported on Linux. It should still work on Windows or MacOS, however the process to do so is far too elaborate to explain here (requries compiling multiple Python libraries).

If you are running a non-Debian derivative system (eg. anything other than Debian, Ubuntu, or Mint), you will need to install your distribution's version of the following:

```
build-essential bzip2 git curl tar python3.7 python3-dev python3.7-dev python3-pip python3-venv
```

Once you have done this, or if you are running a Debian derivative, simply run this command to create an OpenSight instance in your current directory:

```
curl -O https://opensight-cv.github.io/install-opsi.sh
chmod +x install-opsi.sh
./install-opsi.sh
```

or

```
curl https://opensight-cv.github.io/install-opsi.sh | bash
```

!!! warning
    Please only run the one line command if you understand the security implications of it. We recommend you inspect the installation script to ensure it is safe.
