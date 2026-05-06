# Zram-openrc

## About

Init script for zram management with OpenRC.

## Usage

Create a symbolic link in the format `zram.LABEL` to `zram` in `/etc/init.d`, configuration files following the same naming format should go in `etc/conf.d`. After configuration, enable the script with `rc-update add zram.LABEL boot` and start it with `rc-service zram.LABEL start`.

When using a non-preconfigured file system, you can use `@label@` in `zram_storage_mkfs_options` to automatically pass the label. For example, if you want to create a zram device with a FAT32 file system, you can declare `zram_type="fat"` and `zram_storage_mkfs_options="-n @label@ -F 32 -I"`.

### General config

| Name                      | Default | Example                                                            |
| :------------------------ | ------- | :----------------------------------------------------------------- |
| zram_type                 | swap    | swap, btrfs, ext2, ext3, ext4 or fs that can be created using mkfs |
| zram_size                 | 50%     | 25%, 4GiB, 8192MiB                                                 |
| zram_mem_limit            | empty   | 10%, 2GiB, 4096MiB                                                 |
| zram_backing_dev          | empty   | /dev/sda1                                                          |
| zram_writeback_limit      | empty   | 400MiB, relating to the backing device                             |
| zram_writeback_batch_size | empty   | 32, 64...                                                          |
| zram_compressed_writeback | empty   | yes/no                                                             |
| zram_comp_algo            | empty   | lz4, zstd, lzo...                                                  |
| zram_algo_params          | empty   | "level=1 dict=/etc/dictionary"                                     |

### Swap config

| Name               | Default | Example                 |
| ------------------ | ------- | ----------------------- |
| zram_swap_priority | 32767   | between -1 and 32767    |
| zram_swap_discard  | both    | both, once, pages, none |

### Storage config

| Name                             | Default           | Example                     |
| -------------------------------- | ----------------- | --------------------------- |
| zram_storage_mkfs_options        | empty             | custom mkfs options         |
| zram_storage_extra_mkfs_options  | empty             | append custom mkfs options  |
| zram_storage_mount_options       | empty             | custom mount options        |
| zram_storage_extra_mount_options | noatime,nodiscard | append custom mount options |
| zram_storage_mountpoint          | empty             | /tmp                        |
| zram_storage_mode                | empty             | 777, 1777, 0755             |
| zram_storage_owgr                | empty             | nobody:nobody               |

## References

* [Zram docs](https://docs.kernel.org/admin-guide/blockdev/zram.html): Zram module docs.
* [Zram wiki](https://wiki.archlinux.org/title/Zram): Arch Linux wiki for the zram module.

## License

This project is licensed under the [MIT License](https://github.com/Wizarsy/zram-gen-openrc/blob/master/LICENSE)
