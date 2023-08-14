# Why Arch Linux

1. Because you can flex on internet
2. To learn how Linux distributions work
3. Latest and the greatest software

# UEFI vs BIOS

These are types of firmware in your mother board

| UEFI                                       	| BIOS                                                     	|
|--------------------------------------------	|----------------------------------------------------------	|
| New                                        	| Old                                                      	|
| GUID Partition Table                       	| MBR Partition Table                                      	|
| 9 Zettabytes of storage (9 × 10^9 TB)      	| 2TB-16TB (with Advanced Format) of storage               	|
| 128 Primary partitions                     	| 4 Primary partitions                                     	|
| Fast                                       	| Slow                                                     	|
| Graphical interface with mouse support     	| Text based interface                                     	|
| Support UEFI & BIOS Legacy boot modes      	| BIOS only                                                	|
| EFI system partition is used to store data 	| First sector of storage device is used to store the data 	|

---

# Changing MBR to GPT

- Change from Legacy boot mode (BIOS) to UEFI in firmware (You will **NOT** be able to boot to existing OSes after this) 
- Change the partition table from scratch to be GPT (data will be **ERASED**)
- [Converting MBR to GPT](https://wiki.archlinux.org/title/GPT_fdisk#Convert_between_MBR_and_GPT)

---

# Dual Booting

- Create a partition for new Arch Linux system beforehand if a dedicated storage drive is not available

---

# Pre-requsites

- Internet connection
- Pen drive 4GB

---

# Creating the bootable drive

On Windows, follow [these steps](https://wiki.archlinux.org/title/USB_flash_installation_medium#In_Windows)

- Download the ISO
- Verify the ISO
- Find the drive

```shell
lsblk -o model,name,size,label
```

- Create the bootable USB

```shell
dd \
bs=4M \
if=archlinux.iso \
of=/dev/device \
conv=fsync \
oflag=direct \
status=progress
```

---