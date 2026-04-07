# Zram-gen

## About

A simple script to manage swap devices in zram using open-rc.

## Usage

A simple configuration can be done by creating a `zram-gen` file in `/etc/conf.d` with `ZRAM0=true`. All configuration options with example values ​​are available below.

| Name                | Value                                 | Description                                                      |
| :------------------ | :------------------------------------ | :--------------------------------------------------------------- |
| ZRAM*X*             | true, false                           | Controls the activation of zram device                           |
| ZRAM*X*_SIZE        | 25%, 4GiB, 8192MiB                    | Logical size of the zram device                                  |
| ZRAM*X*_MEM_LIMIT   | 2GiB, 1024MiB                         | Memory limit to be used by the zram device                       |
| ZRAM*X*_COMP_ALGO   | lz4, zstd, lzo...                     | Algorithm used by the zram device                                |
| ZRAM*X*_ALGO_PARAMS | "level=1 dict/etc/dictionary"         | Parameters to be passed to the algorithm used by the zram device |
| ZRAM*X*_PRIORITY    | A number less than or equal to 32767  | Zram swap device priority                                        |
| ZRAM*X*_BACKING_DEV | /dev/sda2                             | Backing device to be used by the zram device                     |
| ZRAM*X*_WRITEBACK   | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |

*X* = Zram device index.

## References

* [Zram docs](https://docs.kernel.org/admin-guide/blockdev/zram.html): Zram module docs.
* [Zram wiki](https://wiki.archlinux.org/title/Zram): Arch Linux wiki for the zram module.
* [Zramen](https://github.com/atweiden/zramen): A tool to manage zram swap space.

## License

This project is licensed under the [MIT License](https://github.com/Wizarsy/zram-gen-openrc/blob/master/LICENSE)
