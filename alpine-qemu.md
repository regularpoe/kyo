# TIL - alpine qemu

## Install QEMU

```bash
apt-get install qemu qemu-kvm

dnf install qemu qemu-kvm
```

## Download Alpine image

```
wget https://dl-cdn.alpinelinux.org/alpine/v3.20/releases/x86_64/alpine-standard-3.20.0-x86_64.iso
```

## Create a virtual disk

```bash
qemu-img create -f qcow2 alpine.qcow2 2G
```

## Run QEMU with Alpine image

```bash
qemu-system-x86_64 -m 512M -cdrom alpine-standard-3.20.0-x86_64.iso -hda alpine.qcow2 -boot d
```

## Login as root (no passwd)

`setup-alpine` and follow prompt

## Reboot machine and boot with

```bash
qemu-system-x86_64 -m 512M -hda alpine.qcow2 -boot c
```

