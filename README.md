# Upgrade-Ubuntu-20.04-to-24.04-LTS

## Acknowledgements
- This repo takes a walk through the commands for upgrading Ubuntu 20.04 to 24.04 LTS.
- This repo is prepared as per the blog post available on [tecmint.com](https://www.tecmint.com/upgrade-ubuntu-20-04-to-24-04/)

**Note** : Ubuntu upgrades are sequential, which means:
1. First upgrade from Ubuntu 20.04 LTS to Ubuntu 22.04 LTS.
2. Then upgrade Ubuntu 22.04 LTS to Ubuntu 24.04 LTS.

## Phase - 1 : Upgrading from Ubuntu 20.04 LTS to 22.04 LTS
### Step - 1 : Backup Your Important Files
- It’s always wise to have a backup of your important files in case something goes wrong.
- There are multiple ways to back up your files:
  -- Cloud storage services like Google Drive, Dropbox, or OneDrive.
  -- External hard drives or USB drives.

### Step - 2 : Ensure Your System Is Up-to-Date
- It’s essential to update your current system to ensure everything is patched and up to date.
```
sudo apt update && sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt autoremove -y
```
- Once the updates are complete, reboot your system to apply the changes, which ensures your system is ready for the upgrade.
```
sudo reboot
```
### Step - 3 : Preparing System for Upgrade
1.  Update Manager is the tool that helps you upgrade your system.
   
```
sudo apt install update-manager-core
```

2. Check for LTS releases of the system in the configuration file.
```
sudo nano /etc/update-manager/release-upgrades
```
- Look for the line that reads: **Prompt=normal**
- Change it to: **Prompt=lts**

### Step - 4 : Upgrade the OS
```
sudo do-release-upgrade
```
**Note** : The upgrade may take some time, depending on your system’s speed and your internet connection. During this process, your system will download the necessary packages and make updates to your operating system, which can take anywhere from 30 minutes to 90 minutes, so be patient.

1. Reboot the system to finish upgrade
```
sudo reboot
```

2. Confirm the OS is Ubuntu 22.04 LTS
```
lsb_release -a
```

## Phase - 2 : Upgrading from Ubuntu 22.04 LTS to 24.04 LTS
```
sudo apt update && sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt autoremove -y
sudo reboot
sudo do-release-upgrade
sudo reboot
```
