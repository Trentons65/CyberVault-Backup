### Step 1: Attach and mount USB drive

![[Pi5LAB03_USB.png]]

First you need to verify what device you attached the USB drive to.f 

`sudo lsblk -f`

This command will list the drives attached to your system. You want to ignore the mmcblk device because that is the microSD card port on your Raspberry Pi. 

![[Pi5LAB02_USBdetected.png]]

On my system, this was /dev/sda1 (the partition for the removable flash drive). Then you want to issue the following command:

`sudo mount /dev/sda1 /media`

This will mount the USB flash drive in the /media folder (or directory) so that you can perform the backup.

## Step 2 : Backup your Raspberry Pi

Issue the following command using the tar command to backup your Raspberry Pi:

`sudo tar -cvpzf /media/«replace with a filename of your choice» --exclude=/media --one-file-system /`

![[Pi5Lab02_BackupCommands.png]]

Once you issue this command, it will take a while to completely backup your Raspberry Pi root file system. 

You could follow the same process to backup your /boot partition, replacing / with /boot.
![[Pi5LAB02_BackupFinished.png]]
#### I utilized the TAR command to backup files from main OS to USB
## Alternative backup procedure

***If you are connecting to the Raspberry Pi using SSH, you have the option to backup the Raspberry Pi over the SSH connection to your local computer. This works either through the USB-Ethernet connection or wireless. You will issue the a command similar to the following:***

`ssh (User)@[(Hostname)/ (HostIP)] sudo tar -cvpzf - --one-file-system / > backup.tar.gz`
