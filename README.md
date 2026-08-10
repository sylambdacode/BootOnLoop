# An initramfs-tools script for booting from a loop file.

## Setup

This script relies on the "loop" kernel module. To ensure it is included during the initramfs generation, add the "loop" module name to the `/etc/initramfs-tools/modules` file.

Afterwards, copy this script to the `/etc/initramfs-tools/scripts/local-premount/` directory.

## Usage

To utilize this script, add kernel commands: `root_loop_device` and `root_loop_file`.

- **`root_loop_device`**: This variable refers to the disk partition (formatted as EXT4) where your loop file is situated.

- **`root_loop_file`**: This is the path to your loop file.

## Example

```
root_loop_disk=/dev/sda1 root_loop_file=/test.img root=/dev/loop0p1
```

