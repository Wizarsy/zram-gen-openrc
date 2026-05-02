# Zram-openrc

## About

Init script for zram management with OpenRC.

## Usage

A simple configuration can be done by creating a `zram-gen` file in `/etc/conf.d` with `ZRAM0=true`. All configuration options with example values ​​are available below.

| Name                 | Default | Value                                 | Description                                                      |
| :------------------- | ------- | :------------------------------------ | :--------------------------------------------------------------- |
| zram_type            |         | true, false                           | Controls the activation of zram device                           |
| zram_size            |         | 25%, 4GiB, 8192MiB                    | Logical size of the zram device                                  |
| zram_writeback       |         | 2GiB, 1024MiB                         | Memory limit to be used by the zram device                       |
| zram_writeback_limit |         | lz4, zstd, lzo...                     | Algorithm used by the zram device                                |
| zram_mem_limit       |         | "level=1 dict=/etc/dictionary"        | Parameters to be passed to the algorithm used by the zram device |
| zram_backing_dev     |         | A number less than or equal to 32767  | Zram swap device priority                                        |
| zram_comp_algo       |         | /dev/sda2                             | Backing device to be used by the zram device                     |
| zram_algo_params     |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| zram_idle            |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |
| ZRAM*X*_WRITEBACK    |         | huge, idle, huge_idle, incompressible | Zram device writeback configuration                              |

| Column1 | Column2 | Column3 |
| ------- | ------- | ------- |
| Item1   | Item1   | Item1   |
| Item1   | Item1   | Item1   |
| Item1   | Item1   | Item1   |

*X* = Zram device index.

## References

* [Zram docs](https://docs.kernel.org/admin-guide/blockdev/zram.html): Zram module docs.
* [Zram wiki](https://wiki.archlinux.org/title/Zram): Arch Linux wiki for the zram module.
* [Zramen](https://github.com/atweiden/zramen): A tool to manage zram swap space.

## License

This project is licensed under the [MIT License](https://github.com/Wizarsy/zram-gen-openrc/blob/master/LICENSE)
