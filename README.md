<img src="banner.png" alt="BlissRoms Banner" align="center">  

<p align="center">  
  <a href="https://blissroms.org"><strong>Website</strong></a> |  
  <a href="https://downloads.blissroms.org"><strong>Download</strong></a> |  
  <a href="https://www.paypal.com/donate/?hosted_button_id=J5SLZ7MQNCT24"><strong>Donate</strong></a> |  
  <a href="https://docs.blissroms.org"><strong>Documentation</strong></a> |  
  <a href="https://www.instagram.com/blissroms"><strong>Instagram</strong></a> |  
  <a href="https://t.me/BlissROM_Updates"><strong>Telegram</strong></a>  
</p>  

---  

## BlissRoms  

BlissRoms brings the latest features, optimizations, and a seamless Android experience tailored to your device. Built on top of [AOSP](https://android.googlesource.com) and enhanced by the dedicated [BlissRoms](https://blissroms.org) team, our ROM ensures performance and reliability.  

## Prerequisites for Building BlissRoms  

### System Requirements:  
- **Latest Ubuntu LTS Release** ([Download Here](https://www.ubuntu.com/download/server))  
- **CPU**: Dual-Core or better for faster builds  
- **RAM**: 8GB (16GB recommended for Virtual Machines)  
- **Storage**: 250GB (minimum 170GB for repo and build space)  

### Java Setup:  
Install Java 8 for compatibility:  
```bash  
sudo add-apt-repository ppa:openjdk/ppa  
sudo apt-get update && sudo apt-get upgrade  
sudo apt-get install openjdk-8-jdk  
update-alternatives --config java  # Select Java 8  
update-alternatives --config javac # Select Java 8  
sudo reboot  
```  

### Required Packages:  
Install dependencies in one go:  
```bash  
sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache libgl1-mesa-dev libxml2-utils xsltproc unzip squashfs-tools python-mako libssl-dev ninja-build lunzip syslinux syslinux-utils gettext genisoimage gettext bc xorriso xmlstarlet git-lfs  
```  

## Repository Initialization  

### [Stable Release Source Repo](https://github.com/BlissRoms/stable_releases/tree/universe)
For stable builds, use the following initialization:  
```bash  
repo init -u https://github.com/BlissRoms/stable_releases.git -b refs/tags/v17.8.2-universe --git-lfs
repo sync -c --force-sync --no-tags --no-clone-bundle -j10 --optimized-fetch --prune  
```  

### Staging Source Repo (DON'T REPORT BUGS OR RELEASE):  
```bash  
repo init -u https://github.com/BlissRoms/platform_manifest.git -b universe --git-lfs  
```  

## Build BlissRoms  

Set up your build environment:  
```bash  
. build/envsetup.sh  
blissify [options] deviceCodename  
```  

### Build Options:  
| Option     | Description                                              |  
|------------|----------------------------------------------------------|  
| `-h`       | Show help dialog                                         |  
| `-c`       | Perform a full clean before building                     |  
| `-d`       | Clean device-specific files before building              |  
| `-v`       | Build Vanilla (no added app store) **[Default Option]**  |  
| `-g`       | Include Gapps						|  
| `-f`       | Include FOSS app store solutions **(requires vendor/foss)** |  

### Examples:  
- **Build with GApps**  
  ```bash  
  blissify -g deviceCodename  
  ```  
- **Build with FOSS**  
  ```bash  
  blissify -f deviceCodename  
  ```  
- **Build with GApps and device clean**  
  ```bash  
  blissify -g -d deviceCodename  
  ```  

### Backward Compatibility:  
The legacy `blissify` command remains supported:  
```bash  
blissify deviceCodename  
```  

## Reporting Build Issues  

For issues with builds from the **Stable Release Source Repo**, join our **[Telegram Build Support Group](https://t.me/Team_Bliss_Build_Support)**.  

---  

**Happy Building!** 😊  

---  
