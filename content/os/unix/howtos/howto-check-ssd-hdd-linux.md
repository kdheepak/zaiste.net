+++
title = "How To Check if a Disk is an SSD or an HDD on Linux"
+++

## By using `/sys/block`

Since the kernel version 2.6.29, Linux automatically detects SSD.

Verify the disk:

```bash
cat /sys/block/sda/queue/rotational
```

`1` = HDD / Hard Drive Disk
`0` = SSD / Solid State Disk


It may not work if the disk is a logical device emulated by hardware e.g. a RAID controller.

## By using `lsblk` from `util-linux`

Use `lsblk` from the `util-linux` package:

```bash
lsblk -d -o name, rota
```

```bash
NAME ROTA
sda     0
sdb     0
sdc     1
```

`ROTA` stands for /Rotational Device/. `0` = false, `1` = true.

## By reading random blocks

Read random blocks off the disk

```bash
time for i in `seq 1 1000`; do
    dd bs=4k if=/dev/sda count=1 skip=$(( $RANDOM * 128 )) >/dev/null 2>&1;
done
```

This operation is slow on HDD (few seconds) while fast on SDD (under a second).

