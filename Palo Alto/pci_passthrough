## Things to consider before you start

- Check the supported drivers for your version: https://docs.paloaltonetworks.com/compatibility-matrix/vm-series-firewalls/sr-iov-and-dpdk-drivers
- Check the hypervisor you will install the VM on. As you (might) need to blacklist the driver so Proxmox doesn't use it, ensure that Proxmox's NIC and the Palo NIC do not use the same driver!

```
$ sudo lspci -nnk | grep -i eth
c6:00.0 Ethernet controller [0200]: Broadcom Inc. and subsidiaries BCM57416 NetXtreme-E Dual-Media 10G RDMA Ethernet Controller [14e4:16d8] (rev 01)
	DeviceName: Broadcom 10G Ethernet #1
	Subsystem: Super Micro Computer Inc BCM57416 NetXtreme-E Dual-Media 10G RDMA Ethernet Controller [15d9:16d8]
$ sudo lspci -nnk | grep -A4 XX:XX.X #Copy the PCI ID and check the driver in use
c6:00.0 Ethernet controller [0200]: Broadcom Inc. and subsidiaries BCM57416 NetXtreme-E Dual-Media 10G RDMA Ethernet Controller [14e4:16d8] (rev 01)
	DeviceName: Broadcom 10G Ethernet #1
	Subsystem: Super Micro Computer Inc BCM57416 NetXtreme-E Dual-Media 10G RDMA Ethernet Controller [15d9:16d8]
	Kernel driver in use: bnxt_en
	Kernel modules: bnxt_en
 ```

- Check which bootloader is used (GRUB or systemd-boot)

```
$ sudo efibootmgr -v
# Or
$ sudo bootctl
```

## Configuration
The Proxmox Wiki is pretty good there! https://pve.proxmox.com/wiki/PCI_Passthrough
