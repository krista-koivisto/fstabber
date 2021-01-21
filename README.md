# What is "fstabber"?

fstabber is a simple Bash script that facilitates creation of fstab entries.

Entries are not automatically added to `/etc/fstab`, you will have to do that yourself.

### Usage

#### One-liner

If you just want to run it quickly, you can use the following:

`bash <(wget -qO - https://raw.githubusercontent.com/krista-koivisto/fstabber/master/fstabber)`

The code above will run the latest version of the script without saving it on your system.

#### Cloned from Git

Clone the repository, run `chmod +x fstabber` in the fstabber directoy and run `./fstabber`.

### File System Support

Currently supported file system types are:
 * ext2
 * ext3
 * ext4
 * NTFS (using `ntfs-3g` driver)
 * FAT32 (using `vfat`)
 * FAT16 (using `vfat`)
 * FAT12 (using `vfat`)

### Explicitly Using `ntfs-3g`

Since most Linux distributions symlink `ntfs` to `ntfs-3g`, I opted to simply use `ntfs` as it's cleaner. However, you can launch fstabber with the `explicit` parameter to enforce explicit driver names. Simply launch it using `./fstabber explicit` instead.

### Requirements

Most Linux distributions come with everything here pre-installed:

 * Bash 4.4 or later
 * `ntfs-3g` for NTFS support
 * `vfat` for FAT support
 * `blkid` and `lsblk`

