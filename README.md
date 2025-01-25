# Import Backup

## 1. Plug in the USB

## 2. Mount the USB:
### Replace `/mnt/usb/` with your preferred path.
1. Create a directory: `mkdir -p /mnt/usb/`
2. Mount the drive: `mount /dev/disk/by-id/usb-Generic_Flash_Disk_21120570640543-0\:0 /mnt/usb/`
3. Verify it mounted by running `/mnt/usb/status.sh`. If the file does not exist, then you may not have mounted it correctly.

## 3. Add storage to Proxmox:
1. Go to Datacenter > Storage
2. Click "Add" on the top of all the drives, and select "Directory".
3. Use these settings:

![image](https://github.com/user-attachments/assets/ddf02d18-edbd-4feb-ae50-8b140b7ff313)

## 4. Restore the backup:
1. Go to the node that you mounted the USB on, and select "USB".
2. Select "Backups"
3. Restore the backup. Use these settings:

![image](https://github.com/user-attachments/assets/22d33eb9-de37-4c0f-a941-7e608d2b0f7f)

Change the VMID, Storage, and hostname to your preferred option.

# Remove USB

## 1. Remove storage from Proxmox:
1. Go to Datacenter > Storage
2. Select "USB" and press "Remove".

## 2. Mount the USB:
### Replace `/mnt/usb/` with the path you created in [step 2](https://github.com/The-Dark-Mode/Proxmox-USB/blob/main/README.md#2-mount-the-usb).
1. Unmount the drive: `umount /mnt/usb/`
2. (Optional) Remove the directory: `rm -rf /mnt/usb/`

## 3. Remove the USB
### Ensure that the USB is not flashing before you remove it from the port.
