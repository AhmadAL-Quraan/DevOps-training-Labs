


📌 1. Identify new disk
`lsblk` or `fdisk -l`

📌 2. Create physical volume
sudo `pvcreate DISK_DEVICE`
sudo `pvs`


Example: DISK_DEVICE=/dev/sdb

📌 3. Create volume group
sudo `vgcreate VG_NAME DISK_DEVICE`
sudo `vgs`


Example: VG_NAME=myvg

📌 4. Create logical volumes
Swap LV:
sudo `lvcreate -L 1G -n LV_SWAP_NAME VG_NAME`

Data LV:
sudo `lvcreate -l 100%FREE -n LV_DATA_NAME VG_NAME`


Verify:

sudo `lvs`

📌 5. Configure swap LV
Format swap:
sudo `mkswap /dev/VG_NAME/LV_SWAP_NAME`

Enable swap:
`sudo swapon /dev/VG_NAME/LV_SWAP_NAME`
`swapon --show`

Add swap to /etc/fstab:
`sudo blkid /dev/VG_NAME/LV_SWAP_NAME`


Add this line (using your UUID):

UUID=SWAP_UUID   none   swap   sw   0 0

📌 6. Configure data LV
Format LV as ext4:
`sudo mkfs.ext4 /dev/VG_NAME/LV_DATA_NAME`

Create mount directory:
`sudo mkdir -p MOUNT_POINT`

Mount it:
`sudo mount /dev/VG_NAME/LV_DATA_NAME MOUNT_POINT`


Verify:

`df -h`

📌 7. Make mount persistent
Get UUID:
sudo `blkid /dev/VG_NAME/LV_DATA_NAME`


Add to /etc/fstab:

UUID=DATA_UUID   MOUNT_POINT   ext4   defaults   0 0

🎉 Done — fully generic LVM workflow.